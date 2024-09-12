<template>
    <h1>技能状况</h1>
    <ul>
        <li v-for = "(skills ,index) in skills":key = "index">
            {{ skills.name }}-
            <span v-if = "skills.unlocked === true" style="color:green">已解锁</span>
            <span v-else style="color: red;">未解锁</span>
        </li>"
       
    </ul>
    
</template>

<script setup lang="ts">
import {ref} from 'vue'

interface Skills {
    name : string 
    unlocked : boolean
}

const skills = ref<Skills[]>([
    {name:"七十二变" , unlocked:true},
    {name:"火眼金睛" , unlocked:false},
    {name:"筋斗云" , unlocked:true}
]) 


</script>

