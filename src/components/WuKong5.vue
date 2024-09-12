<template>
<div>
    <div>
        基础攻击力：
        <input v-model="baseAttack" type="number"/>
    </div>
    <div>
        装备加成：
        <input v-model="gearBonus" type="number"/>
    </div>
    <p>总攻击力：{{ totalAttack }}</p>
</div>
</template>

<script setup lang="ts">
import {computed ,ref } from 'vue'

const baseAttack = ref<number>(50)
const gearBonus = ref<number>(20)

const totalAttack = computed(() => baseAttack.value + gearBonus.value)
</script>

<style scoped>
div
{
    margin-bottom: 10px;
    padding: 10px;
    background-color: white;
    border-radius: 5px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

input[type = "number"]
{   width:100%;
    padding: 8px;
    border: 1px solid #ccc;
    border-radius: 4px;
    font-size: 16px;
}


</style>