<template>
	  <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8 mt-5">
                <div class="card">
                    <div class="card-header">
                        Watch Properties Example
                       	<!-- Data'lar üzerinde anlık değişimleri gözlemleyebilmemiz ve bunlar üzerinde işlem yapabilmemizi sağlıyor -->
                    </div>  
                    <div class="card-body">
                       <div class="form-group">
                       	<label>Ad Soyad</label>
                       	<!-- 
                       	inputtaki veri uzunluğu sıfırdan büyükse kırmızı
						inputtaki veri uzunluğu sıfıra eşitse ve name verisi boş değilse yeşil
                       	 -->
                       	<input type="text" v-model="name" class="form-control" 
                       	v-bind:class="{ 'is-invalid':errors.length>0, 'is-valid':errors.length==0 && name!='' }">
                       	<!-- error'daki verileri ekrana yaz -->
                       	<div class="invalid-feedback">
                       		<span :key="key" v-for="(error,key) in errors">
                       			{{error}}
                       		</span>
                       	</div>
                       </div>
                       <!-- error uzunluğu sıfırdan büyük ya da name verisi boş ise butonu işlevsiz yap -->
                       <button :disabled="errors.length>0 || name==''" @click="create" class="btn btn-primary">Oluştur</button>
                    </div>  
                </div>  
                <user-list @deleteUser="deleteUsers" :users="users"></user-list>
                             
            </div>
        </div>
    </div>
</template>
<script>
  import userList from './userList.vue'
	export default {//diğer sayfaya veri gönderme
    components:{
      userList
    },
		data(){
			return{
				name:'',
				errors:[],
				users:[]
			}
		},
		watch:{
			name(val){
				this.errors=[]
				if(val==''){
					this.errors.push('Ad Soyad Alanı Boş Bırakılamaz!')
					return;
				}
				if (val[0]!==val[0].toUpperCase()) {
					this.errors.push('İlk Harf Büyük Olmalıdır!')
					return;

				}

				if(val.length<6 || val.length>24){
					this.errors.push('Ad Soyad Alanı Minumum 6 Makimum 24 Karakter Olmalıdır!')
					return;
				}


				
			}
			
		},
		methods:{
			create(){ //kullanıcı ekle
				this.users.push(this.name)
        this.name=''
			},
			deleteUsers(key){ //kullanıcı sil
				this.$delete(this.users,key)
			}
		}
	}
</script>
<style>
	
</style>