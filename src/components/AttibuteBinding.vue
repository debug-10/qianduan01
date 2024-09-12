<template>
    <div> 
        <!-- <button :disabled = "isDisabled">点击</button>  -->

        <button v-bind = "buttonAttrs">点击我</button>
    </div>
</template>

<script lang="ts">
import { reactive, ref } from 'vue'
// const isDisabled = ref<boolean>(false)

const buttonAttrs = reactive ({
    disabled : false,
    title : '按钮已禁用',
    id: 'unique-button',
})



</script>
