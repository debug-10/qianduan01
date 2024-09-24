<template>  
  <div>  
    <el-table :data="tableData.slice((currentPage-1)*pageSize, currentPage*pageSize)" style="width: 100%">  
        <el-table-column prop="date" label="日期" width="180"></el-table-column>  
    <el-table-column prop="name" label="姓名" width="180"></el-table-column>  
    <el-table-column prop="address" label="地址"></el-table-column>
    </el-table>  
    <el-pagination  
      @size-change="handleSizeChange"  
      @current-change="handleCurrentChange"  
      :current-page="currentPage"  
      :page-sizes="[5, 10, 20, 30, 40]"  
      :page-size="pageSize"  
      layout="total, sizes, prev, pager, next, jumper"  
      :total="tableData.length">  
    </el-pagination>  
  </div>  
</template>  
  
<script>  
export default {  
  data() {  
    return {  
      tableData: [
        {data:"2024-10-01",name:"A",address:"南京"},
        {data:"2024-10-02",name:"B",address:"南京"},
        {data:"2024-10-03",name:"C",address:"南京"},
        {data:"2024-10-04",name:"D",address:"南京"},
        {data:"2024-10-05",name:"E",address:"南京"},
        {data:"2024-10-06",name:"F",address:"南京"},
        {data:"2024-10-07",name:"G",address:"南京"},
        {data:"2024-10-08",name:"H",address:"南京"},
        {data:"2024-10-09",name:"I",address:"南京"},
        {data:"2024-10-10",name:"J",address:"南京"},
        {data:"2024-10-11",name:"K",address:"南京"},
        {data:"2024-10-12",name:"L",address:"南京"},
        {data:"2024-10-13",name:"M",address:"南京"},
        {data:"2024-10-14",name:"N",address:"南京"},
        {data:"2024-10-15",name:"O",address:"南京"},

    ],  
      currentPage: 1,  
      pageSize: 10  
    };  
  },  
  methods: {  
    handleSizeChange(val) {  
      this.pageSize = val;  
      this.currentPage = 1;  
    },  
    handleCurrentChange(val) {  
      this.currentPage = val;  
    }  
  }  
};  
</script>