<template>  
  <div class="hobby-survey">  
    <h1>兴趣爱好调查</h1>  
    <el-form ref="hobbyForm" :model="hobbyForm" class="hobby-form">  
      <el-form-item label="兴趣爱好" class="form-item">  
        <!-- 全选/全不选 -->  
        <el-checkbox v-model="isAllSelected" @change="handleAllSelect" class="checkbox-all">全选</el-checkbox>  
        <el-checkbox-group v-model="hobbyForm.hobbies" @change="handleHobbyChange" class="checkbox-group">  
          <el-checkbox  
            v-for="(hobby, index) in hobbies"  
            :key="index"  
            :label="hobby.value"  
            :indeterminate="isIndeterminate"  
            class="checkbox-item"  
          >  
            {{ hobby.label }}  
          </el-checkbox>  
        </el-checkbox-group>  
        <!-- 动态添加选项 -->  
        <div class="add-new-hobby">  
          <el-input v-model="newHobby" placeholder="输入新的兴趣爱好" class="input-new-hobby"></el-input>  
          <el-button type="primary" @click="addNewHobby" class="button-add">添加</el-button>  
        </div>  
      </el-form-item>  
      <el-form-item class="form-item">  
        <p class="selected-hobbies">已选择的兴趣爱好：{{ hobbyForm.hobbies.join(', ') }}</p>  
      </el-form-item>  
      <el-form-item>  
        <el-button type="primary" @click="submitForm">提交</el-button>  
      </el-form-item>  
    </el-form>  
  </div>  
</template>  
  
<script>  
export default {  
  data() {  
    return {  
      hobbyForm: {  
        hobbies: []  
      },  
      hobbies: [  
        { value: 'reading', label: '阅读' },  
        { value: 'traveling', label: '旅行' },  
        { value: 'coding', label: '编程' },  
         
      ],  
      newHobby: '',  
      isAllSelected: false,  
      isIndeterminate: false  
    };  
  },  
  methods: {  
    handleAllSelect(value) {  
      this.hobbyForm.hobbies = value ? this.hobbies.map(hobby => hobby.value) : [];  
      this.isIndeterminate = false;  
    },  
    handleHobbyChange(value) {  
      this.isAllSelected = this.hobbyForm.hobbies.length === this.hobbies.length;  
      this.isIndeterminate = this.hobbyForm.hobbies.length > 0 && this.hobbyForm.hobbies.length < this.hobbies.length;  
    },  
    addNewHobby() {  
      if (this.newHobby.trim() !== '') {  
        this.hobbies.push({ value: this.newHobby, label: this.newHobby });  
        this.hobbyForm.hobbies.push(this.newHobby);  
        this.isAllSelected = false;  
        this.isIndeterminate = true;  
        this.newHobby = '';  
      }  
    },  
    submitForm() {  
      alert('提交的兴趣爱好: ' + this.hobbyForm.hobbies.join(', '));  
    }  
  }  
};  
</script>  
  
<style scoped>  
.hobby-survey {  
  max-width: 600px;  
  margin: 0 auto;  
  padding: 20px;  
  background-color: #f9f9f9;  
  border-radius: 8px;  
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.1);  
}  
  
.hobby-form {  
  margin-top: 20px;  
}  
  
.form-item {  
  margin-bottom: 20px;  
}  
  
.checkbox-all {  
  margin-right: 10px;  
    margin-bottom: 10px;  
}  
  
.checkbox-group {  
  display: flex;  
  flex-wrap: wrap;  
  margin-bottom: 10px;  
}  
  
.checkbox-item {  
  margin-right: 10px;  
  margin-bottom: 10px;  
}  
  
.add-new-hobby {  
  display: flex;  
  align-items: center;  
}  
  
.input-new-hobby {  
  flex: 1;  
  margin-right: 10px;  
}  
  
.button-add {  
  min-width: 80px;  
}  
  
.selected-hobbies {  
  margin: 0;  
  color: #333;  
}  
</style>