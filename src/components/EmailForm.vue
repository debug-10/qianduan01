<template>  
    <div class="form-container">  
        <form @submit.prevent="submitForm" class="form">  
            <input type="text" placeholder="请输入邮箱" v-model="form.to" class="form-input" />  
            <input type="text" placeholder="请输入主题" v-model="form.subject" class="form-input" />  
            <textarea placeholder="请输入内容" v-model="form.body" class="form-textarea"></textarea>  
            <button type="submit" class="form-button">发送</button>  
        </form>  
    </div>  
</template>

<script setup lang="ts">
import { reactive } from 'vue';


const form = reactive({
    to:"2319780642@qq.com",
    subject:"",
    body:"",
})


const emit = defineEmits<{'submit-form': [any]}>()

const submitForm = () => {
    emit('submit-form', form);
    
};
</script>

<style scoped>  
.form-container {  
    max-width: 400px;  
    margin: 20px auto;  
    padding: 20px;  
    border: 1px solid #ccc;  
    border-radius: 8px;  
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);  
}  
  
.form {  
    display: flex;  
    flex-direction: column;  
    gap: 10px;  
}  
  
.form-input,  
.form-textarea {  
    padding: 10px;  
    border: 1px solid #ddd;  
    border-radius: 4px;  
    font-size: 16px;  
    width: 100%;  
    box-sizing: border-box;  
}  
  
.form-textarea {  
    height: 100px;  
    resize: vertical;  
}  
  
.form-button {  
    padding: 10px 20px;  
    background-color: #007bff;  
    color: white;  
    border: none;  
    border-radius: 4px;  
    cursor: pointer;  
    font-size: 16px;  
    transition: background-color 0.3s;  
}  
  
.form-button:hover {  
    background-color: #0056b3;  
}  
</style>