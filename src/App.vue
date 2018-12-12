<template>
	<div id="app">
		<h1>在线翻译</h1>
		<span class="text-muted">
			Made by ZYT
		</span>
		<Transform @toTransform='toTransform'></Transform>
		<transformOutput :readyTransform='readyTransform'></transformOutput>
	</div>
</template>

<script>
	//import HelloWorld from './components/HelloWorld'
	import Transform from './components/Transform'
	import transformOutput from './components/transformOutput'

	export default {
		name: 'App',
		data() {
			return {
				readyTransform: ''
			}
		},
		components: {
			Transform,
			transformOutput,
		},
		methods: {
			toTransform: function(toTransform, language) {
				this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20181212T133311Z.4924d65f8583ecd5.46d765905a3b0eda360427092af3348677a1b4eb&lang=' + language + '&text=' + toTransform)
					.then((response => {
						//				console.log()response.body.text[0];
						this.readyTransform = response.body.text[0];

					}))
			}
		}
	}
</script>

<style>
	#app {
		margin: 0;
		padding: 0;
		border: 0;
		overflow:hidden;overflow-y:auto;
		margin-top: 60px;
		text-align: center;
	}
</style>