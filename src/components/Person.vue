<template>
    <div>
        <div> name: {{name}}</div>
        <div> age: {{age}}</div>
        <div> tel: {{tel}}</div>
        <button @click="changeName">修改名字</button>
        <hr>
        <div>汽车品牌: {{ car.band }}</div>
        <button @click="changeCar">修改汽车</button>
        <hr>

    </div>
</template>

<script lang="ts">
    import { ref, reactive } from "vue"
    export default {
        name:'Person'
    }
</script>

<script setup lang="ts">
    let name = ref('小样') //ref是基础数据和对象都可以
    let age = 18
    let tel = 18888888888
    let car = reactive({band: '奔驰', price: 100}) // 只能对象

    function changeName(){
        name.value = 'xiaoyang';
    }
    function changeCar(){
        car.band = 'BMW'
    }




</script>