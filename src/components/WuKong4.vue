<template>
    <div>
        <div class = "hp-bar">
    <div class = "hp-bar-fill" :style="{width :percentage + '%'}"> </div>
         </div>
        <p >血量：{{ hp }}/{{ thp }}({{ percentage.toFixed(2)}}%)</p>
    </div>
</template>

<script setup lang="ts">
import { computed, ref } from 'vue';

// 总血量
const thp = ref<number>(100)

//攻击
const attack = ref<number>(40)

//现血量
const hp = computed( ()=> {
    return thp.value - attack.value
})

//血量百分比
const percentage = computed( () => {
    return (hp.value / thp.value)*100
})
</script>


<style>


.hp-bar {
    width: 100%;
    height: 20px;
    background-color: #ddd;
    border-radius: 10px;
    margin: 10px 0;
    overflow: hidden;
}

.hp-bar-fill{
    height: 100%;
    width: 0px;
    background-color: green;    
    border-radius: 10px;
    transition: width 0.3s ease-in-out;
}

</style>
