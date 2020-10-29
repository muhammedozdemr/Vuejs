<template>
	<!-- kullanıcı var ise listeyi göster yok ise gösterme -->
	<div v-if="users.length>0" class="card mt-5">
        <div class="card-header">
                        Üye Listesi
        </div>  
        <div class="card-body">
                    	<!-- kullanıcıyı listele -->
            <li :key="key" v-for="(user,key) in users">
                {{user}}
                       		<!--kullanıcıyı sil -->
                <button class="btn btn-danger btn-sm" @click="$emit('deleteUser',key)">Sil</button>
            </li>
                   	
        </div>  
    </div>   
</template>

<script>
	export default {//diğer sayfadan gelen veriyi yakala
		
		props:['users']
	}
</script>

<style>
	
</style>