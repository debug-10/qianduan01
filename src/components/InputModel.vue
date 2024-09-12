<template>
    <div>
        <!-- <input v-model="name" placeholder="请输入姓名"/>
        <p>您输入的姓名是：{{ name }}</p> -->

        <!-- <input type="checkbox" v-model="isChecked"/>
        <p>复选框状态：{{ isChecked }}</p> -->
 
        <!-- <input type="radio" v-model="selectedOption" value="A"/>
        <input type="radio" v-model="selectedOption" value="B"/>
        <p>您的选项是：{{ selectedOption }}</p> -->
<!-- 
        <div>
            <select v-model="selectedItem">
                <option disabled value="">请选择一个选项</option>
                <option value="苹果">苹果</option>
                <option value="香蕉">香蕉</option>
                <option value="橘子">橘子</option>
            </select>
            <p>您选择的水果是：{{ selectedItem }}</p>
        </div> -->

        <!-- <label><input type="checkbox" v-model="selectedFruits" value="苹果"/>苹果</label>
        <label><input type="checkbox" v-model="selectedFruits" value="香蕉"/>香蕉</label>
        <label><input type="checkbox" v-model="selectedFruits" value="橘子"/>橘子</label>
        <p>您选择的水果是：{{ selectedFruits.join(',') }}</p> -->
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import { ssrLooseContain } from 'vue/server-renderer';
// const name = ref<string>('')
// const isChecked = ref<boolean>(false)
// const selectedOption = ref<string>('A')
// const selectedItem = ref<string>('')
// const selectedFruits = ref<string[]>([])

</script>

<style scoped>

</style>