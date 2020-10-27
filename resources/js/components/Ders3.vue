<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8 mt-5">
                <div class="card">
                    <div class="card-header">
                        Class & Style İşlemleri
                    </div>  
                    <div class="card-body">
                        <!-- renk değiştir butonuna tıklandığında yazı rengini kırmızı yap
                            yazı boyutunu değiştir butonuna tıklandığında yazı boyutunu büyüt
                        <p v-bind:class="{'text-danger':red,'buyut':size}">Merhaba ben Muhammed</p> 
                        <button @click="red=!red">Renk Değiştir</button>
                        <button @click="size=!size">Yazı Boyutu Değiştir</button> -->
                        <!--<label>Ad Soyad</label>
                        girilen veri uzunluğu 3'ten büyükse yeşil değilse kırmızı uyarı versin 
                        <input type="text" class="form-control" v-bind:class="[name.length>3 ? 'is-valid' : 'is-invalid']" v-model="name">-->
                        <p v-bind:style="myStyle">
                            Lorem ipsum dolor sit amet consectetur adipisicing elit. Quam at error iusto perferendis 
                            laudantium ab tenetur nisi ipsam praesentium tempore! Corrupti quod, eum sed reiciendis 
                            ratione magni possimus impedit corporis?
                        </p>
                    </div>  
                </div>               
            </div>
        </div>
    </div>
</template>

<script>
export default{
    data(){
        return {
            //red:false,
            //size:false,
            name:'',
            myStyle:{
                color:'red',
                fontSize:'50px'
            }
        }
    },

}
</script>

<!--<style>
.kirmizi{
    color:red;
}
.buyut{
    font-size:50px;
}
</style>-->