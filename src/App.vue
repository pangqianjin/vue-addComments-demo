<template>
	<div>
		<h1>请发表对Vue和React的评论</h1>
		<div id="content">
			<Add id="add" :addComment="addComment" />
			<Comments id="comment" :comments="comments" :deleteComment="deleteComment" />
		</div>
	</div>
</template>

<script>
	import Add from './components/Add.vue'
	import Comments from './components/Comments.vue'

	export default {
		data(){
			return {
				comments: [],
			}
		},
		methods:{
			addComment:function(item){
				this.comments.unshift(item)
			},
			deleteComment:function(index){
				this.comments.splice(index, 1)
			}
		},
		components: {
			Add,
			Comments
		}
	}
</script>
<style>
	#content {
		display: flex;
	}
	#add{
		margin: 2em;
	}
</style>
