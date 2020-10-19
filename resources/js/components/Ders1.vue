<template>
<div align="center">
<button @click="ageCounter('+',1)" class="btn btn-primary">1 Yaş Arttır</button>	
<button @click="ageCounter('+',-3)" class="btn btn-warning">3 Yaş Azalt</button>	
	Merhaba <span v-html="isim"></span> 
	Yaşınız {{yas}} 
	<h5 v-if="yas>=18">Reşitsiniz</h5>
	<h5 v-else>Reşit Değilsiniz</h5>
</div>
</template>

<script>

export default {
	data(){
		return{
			isim:'<strong>Muhammed</strong>',
			yas:14			
		}

	},
	methods:{
		ageCounter(command,age){
		if(command=='+'){
			this.yas+=age
			}
			else
			{
			this.yas-=age
			}
		}
		
	},
	beforeCreate(){
	console.log('beforeCreate')
	},
	created(){
	console.log('created')
	},
	beforeMount(){
	console.log('beforeMount')
	},
	mounted(){
	this.ageCounter('+',5)
	},
}

</script>

<style scoped>

</style>