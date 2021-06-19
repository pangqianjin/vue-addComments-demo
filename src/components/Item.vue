<template>
	<div id="item">
		<button id="btn" type="button" @click="deleteComment(index)">删除</button>
		{{comment.username}}说：<br>
		<p>{{comment.content}}</p>
	</div>
</template>

<script>
	export default{
		props:{
			comment:{
				type:Object,
				required:true
			},
			index:{
				type:Number,
				required:true
			},
			deleteComment:{
				type:Function,
				required:true
			}
		}
	}
</script>

<style>
	#item{
		border: solid 1px;
		width: 300px;
		height: 100px;
	}
	#btn{
		float: right;
	}
</style>
