<template>
    <div>
        <p>用户名：{{ user.name }}</p>
        <p>年龄:{{ user.age }}</p>
    <button @click="increaseAge">增加年龄</button>

    </div>
</template>

<script setup lang="ts">
import {reactive} from 'vue'

const user = reactive<{name: string ;age: number}>({
    name: '张三',
    age: 25
})

const increaseAge = ():void => {
    user.age++
}
</script>

<style scoped>

</style>