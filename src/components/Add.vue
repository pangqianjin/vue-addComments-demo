<template>
	<div>
		用户名:<br>
		<input type="text" placeholder="请输入用户名" v-model="username" /><br><br>
		你的看法:<br>
		<textarea rows="5" cols="30" v-model="content" placeholder="请输入你的看法"></textarea><br>
		<button type="button" @click="submit">提交</button>
	</div>
</template>

<script>
	export default{
		props:{
			addComment:{
				type:Function,
				required: true
			}
		},
		data(){
			return {
				username: '',
				content: ''
			}
		},
		methods:{
			tradeNo:function () {
			  const now = new Date()
			  const year = now.getFullYear();
			  let month = now.getMonth() + 1;
			  let day = now.getDate();
			  let hour = now.getHours();
			  let minutes = now.getMinutes();
			  let seconds = now.getSeconds();
			  String(month).length < 2 ? (month = Number("0" + month)) : month;
			  String(day).length < 2 ? (day = Number("0" + day)) : day;
			  String(hour).length < 2 ? (hour = Number("0" + hour)) : hour;
			  String(minutes).length < 2 ? (minutes = Number("0" + minutes)) : minutes;
			  String(seconds).length < 2 ? (seconds = Number("0" + seconds)) : seconds;
			  const yyyyMMddHHmmss = `${year}${month}${day}${hour}${minutes}${seconds}`;
			  return yyyyMMddHHmmss + '_' + Math.random().toString(36).substr(2, 9);
			},
			submit:function(){
				if(!this.username || !this.content){
					alert('用户名或看法不能为空!')
					return
				}
				const username = this.username.trim()
				const content = this.content.trim()
				const id = this.tradeNo()
				this.addComment({username, content, id})
				this.username=''
				this.content=''
			}
		}
	}
</script>

<style>
</style>
