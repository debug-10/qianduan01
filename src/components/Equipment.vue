<template>
    <div>
        <h1>装备管理</h1>
        <form @submit.prevent = "addEquip">
            <input type="text" v-model="equip.name" placeholder="装备名称"/>
            <button type = "submit" >添加装备</button>
        </form>
        <ul>
            <li v-for="equipment in equipments" :key = "equipment.id">
            {{ equipment.name }}
            <button @click = "removeEquip(equipment.id)">删除</button>
            </li>
        </ul>
    </div>
</template>

<script setup lang="ts">
import {ref } from 'vue';

interface Equip {
    id : number;
    name : string;
}

const equipments = ref<Equip[]>([])

const equip = ref<Equip>({ id:0 ,name : ''});

const addEquip = () => {
    if (equip.value.name.trim()){
        equip.value.id = equipments.value.length +1;
        equipments.value.push(equip.value);
        equip.value = { id : 0 , name :''};
    }
};

const removeEquip = (id : number) => {
    equipments.value = equipments.value.filter(equipment => equipment.id !== id);
};
</script>

<style scoped>

/* 容器 */
div {
    max-width: 600px;
    margin: 20px auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

/* 标题 */
h1{
    text-align: center;
    color: #333;
}

/* 表单 */
form{
    display: flex;
    justify-content: space-between;
    margin-bottom: 20px;
}

/* 输入框 */
input[type = "text"]
{   flex-grow: 1;
    padding: 1;
    margin-right: 10px;
    border:1px solid #ccc;
    border-radius: 4px;
    font-size: large;

}
</style>