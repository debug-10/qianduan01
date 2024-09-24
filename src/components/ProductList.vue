<template>
  <el-card>
    <h2>商品列表</h2>

    <el-table :data="products">
        <el-table-column prop="name" label="商品名称"></el-table-column>
        <el-table-column prop="price" label="价格"></el-table-column>
        <el-table-column prop="操作">
            <template #default="{ row }">
                <el-button type="primary" @click="showProductDetail(row)">
                    查看详情
                </el-button>
            </template>
        </el-table-column>
    </el-table>
  </el-card>
</template>

<script setup lang="ts">
import { ElCard , ElTable , ElButton, ElTableColumn } from "element-plus";
import { ref } from "vue"
import "element-plus/dist/index.css"

interface Product{
    name : string;
    price : number;
}

const products = ref<Product[]>([
    {name:"商品A" ,price : 100},
    {name:"商品B" ,price : 200},
    {name:"商品C" ,price : 300},
]);

const showProductDetail = (product: Product) => {
    alert(JSON.stringify(product));
}
</script>

<style scoped>
.el-card{
    max-width: 800px;
    margin: 20px auto;
}

</style>