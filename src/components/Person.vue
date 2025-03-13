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
        <div>我的名字:{{ myName }} - toRefs的使用</div>
        <button @click="changeMyName">修改名字</button>
        <hr>
        <div>姓：<input v-model="firstName"></div>
        <div>名：<input v-model="lastName"></div>
        <div>全名：{{ fullName }}</div>
    </div>
</template>

<script lang="ts">
    import { ref, reactive, toRefs, computed } from "vue"
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

    // ----------------

    let person = reactive({myName: 'jack', myHome: 'shjs'})
    let {myName, myHome} = toRefs(person)
    function changeMyName(){
        myName.value = 'rose'
    }

    // ----------------
    let firstName = ref('zhang')
    let lastName = ref('san')
    let fullName = computed(() => {
        return firstName.value + '-' + lastName.value
    })

</script>