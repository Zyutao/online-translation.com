<template>
	<div class="transformOutput">
		<p>{{readyTransform}}</p>
	</div>
</template>

<script>
	export default {
		name: 'transformOutput',
		data(){
			return{
			
			}
		},
		props:{
			readyTransform:String,
			required:true
		},
		
	}
</script>

<style>

</style>