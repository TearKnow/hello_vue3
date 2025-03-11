<template>
    <div>
        <div> name: {{name}}</div>
        <div> age: {{age}}</div>
        <div> tel: {{tel}}</div>
        <button @click="changeName">修改名字</button>
    </div>
</template>

<script lang="ts">
    import { ref } from "vue"
    export default {
        name:'Person'
    }
</script>

<script setup lang="ts">
    let name = ref('小样')
    let age = 18
    let tel = 18888888888

    function changeName(){
        name.value = 'xiaoyang';
    }
</script>