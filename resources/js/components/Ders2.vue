<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8 mt-5">
                <div class="card-body">

                    <div class="card-header">
                        Form İşlemleri
                    </div>
                    <div class="card-body">
                        <div class="form-group">
                        <label>Ad</label>
                        {{name}}
                        <input type="text" v-model="name" class="form-control"> <!--kullanıcı tarafından girilen text'i belirtilen değişkenin yerine yazar-->
                        <!-- <input type="number" v-model.number="name" class="form-control"> kullanıcı tarafından girilen number'i belirtilen değişkenin yerine yazar-->
                        <!--<input type="text" v-model.lazy="name" class="form-control"> lazy=>kullanıcı tarafından girilen veriyi anlık olarak değilde işlem bittikten sonra ekrana yazdırır. -->
                        </div>
                        <div class="form-group">
                            <span :key="key" v-for="(singular,key) in select">
                                {{options.find(item =>item.value==singular).name}} seçildi.<br>
                            </span>
                            
                            <select class="form-control" multiple v-model="select">
                                <option :value="option.value" :key="key" v-for="(option,key) in options">
                                    {{option.name}}
                                </option>
                            </select>
                        </div>
                        <div class="form-group">
                           <label>Radio Button</label><br>
                           {{radio}}
                            <input type="radio" id="bir" value="0" v-model="radio">  
                            <label for="bir">Elma</label>                          
                            <input type="radio" id="iki" value="1" v-model="radio">
                            <label for="iki">Armut</label>
                        </div>
                        <div class="form-group">
                            <label>Checkbox</label><br>
                            {{checkbox}}
                            <input type="checkbox" id="elma" value="Elma" v-model="checkbox">
                            <label for="elma">Elma</label>
                            <input type="checkbox" id="armut" value="Armut" v-model="checkbox">
                            <label for="armut">Armut</label>
                            <input type="checkbox" id="kiraz" value="Kiraz" v-model="checkbox">
                            <label for="kiraz">Kiraz</label>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default{
    data:()=>({
        name:null,
        options:[
            {name:'Belirtmek istemiyorum',value:0},
            {name:'Erkek',value:1},
            {name:'Kadın',value:2}


                ],
        select:[0],
        radio:1,
        checkbox:[]
    })
}
</script>

<style>
</style>