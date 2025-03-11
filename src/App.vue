<template>
    <div class="app">
        My App:
        <Person></Person>
    </div>
</template>

<script lang="ts">
  import Person from './components/Person.vue'
  export default {
    name:'App', //组件名
    components:{Person} //注册组件
  }
</script>

<style>
    .app{
        background: #ddd;
        border: 1px solid #ddd;
    }
</style>