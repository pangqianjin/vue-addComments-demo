<template>
	<div>
		<h2>评论回复</h2>
		<h3 v-show="comments.length===0">暂无评论</h3>
		<Item v-for="(comment, index) in comments"
			key="comment.id" :comment="comment"
			:deleteComment="deleteComment" :index="index" />
	</div>
</template>

<script>
	import Item from './Item.vue'
	
	export default{
		props:['comments', 'deleteComment'],
		components:{
			Item
		}
	}
</script>

<style>
</style>
