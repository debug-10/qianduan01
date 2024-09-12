<template>
 <div>
    <!-- <input v-model.lazy="name"  placeholder="请输入姓名" />
        <p>您输入的姓名是：{{ name }}</p> -->

        <input v-model.trim ="username"  placeholder="请输入用户名" />
        <p>您的用户名是：{{ username }}</p>
 </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

// const name = ref<string>('')

const username = ref<string>('')
</script>

<style scoped>

</style>