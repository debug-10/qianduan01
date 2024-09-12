<template>
    <div>
        <p :class = "pClass">这是一段文字</p>
        <button @click = "toggleClass">切换样式</button>

    </div>
</template>

<script setup lang="ts">
import {ref} from 'vue'

const isHighLingt = ref<boolean>(false)

    //动态切换的样式名
const pClass = ref<{[key: string] : boolean }>({
    isHighLingt : isHighLingt.value,
    normal : !isHighLingt.value,
})

    //切换类名的函数
const toggleClass = () => {
    isHighLingt.value = !isHighLingt.value
    pClass.value = {
        isHighLingt : isHighLingt.value,
        normal : !isHighLingt.value,
    }

}
</script>

<style scoped>
.isHighLight{
    color : red;
}

.normal{
    color : black;
}

</style>