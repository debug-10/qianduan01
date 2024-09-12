<template>
   <div>
    <h2>当前用户:{{ userName }}</h2>
    <button @click="changName">切换</button>
    </div>
    </template>
    
    <script setup lang="ts">
    import {ref} from 'vue'
    const userName=ref<string>('孙悟空')
    
    const changName=()=>{
     userName.value='斗战圣佛'
    }
    </script>
    
    <style>
    div{
        background-color: greenyellow;
        text-align: center;
        border-radius: 10px;
    }

    h2{
    font-size: 24px;
    color:red;
    margin-bottom: 10px;
}

    </style>