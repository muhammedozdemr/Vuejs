<template>
	  <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8 mt-5">
                <div class="card">
                    <div class="card-header">
                        Watch Properties
                       	<!-- Data'lar üzerinde anlık değişimleri gözlemleyebilmemiz ve bunlar üzerinde işlem yapabilmemizi sağlıyor -->
                    </div>  
                    <div class="card-body">
                       <h1 v-if="alert">Sayı {{counter}} 'a ulaştı.</h1>
                       Sayı : {{counter}}
                       <button @click="counter++">Arttır</button>
                       <button @click="counter--">Azalt</button>
                    </div>  
                </div>               
            </div>
        </div>
    </div>
</template>
<script>
	export default {
		data(){
			return{
				counter:0,
				alert:false

			}
		},
		methods:{
			artir(){
				this.alert=true
			}
		},
		watch:{
			counter(val,oldval){
				if(val>oldval)
				{
					console.log('Sayı Arttırıldı')
					if(val>9){
						this.artir()
					}
				}
				else{
					console.log('Sayı Azaltıldı')
				}
			}
		}
	}
</script>
<style>
	
</style>