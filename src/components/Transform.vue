<template>
	<div id="transform" class="row">
		
		<div class="col-md-12 col-md-offset-3 form-group has-success">
			<form class="" v-on:submit="formSubmit" >
				<input class="form-control is-valid inp" type="text" v-model="toTransform"  placeholder="请输入需要翻译的内容"/>
				<select class="has-success form-control sel" v-model="language">
					<option value="en">English</option>
					<option value="fr">French</option>			
					<option value="it">Italian</option>
					<option value="ko">korean</option>
				</select>
				<input class="btn btn-info" type="submit" value="翻译"/>
			</form>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'transform',
		data() {
			return {
				toTransform:"",
				language:"en"
			}
		},
		methods:{
			formSubmit(e){				
				
				e.preventDefault();
				this.$emit('toTransform',this.toTransform,this.language)
			}
		}
	}
</script>

<style scoped>
#transform {
		margin-top: 10px;
		text-align: center;
	}
.inp{
	width: 300px;
	display: inline-block;
}
.sel{
	width: 100px;
	display: inline-block;
}
form{
	
}
</style>