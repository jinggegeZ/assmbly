<template>
 <div>
  <jing-table :tableData="tableData" :cloumns="cloumns">
    <template v-slot:state="scope">
      <el-switch v-model="scope.scope.roe"></el-switch>
    </template>
    <template v-slot:action="scope">
      <el-button type="danger" @click="delete(scope.scope)" size="mini">删除</el-button>
      <el-button type="danger" @click="choseedit(scope.scope)" size="mini">编辑</el-button>
      <!-- <el-button type="danger" @click="delete(scope.scope)" size="mini">分配角色</el-button> -->
    </template>
  </jing-table>
 </div>
</template>

<script>
 export default {
   name: '',
   props: {
   },
   components: {

   },
   data () {
     return {
       tableData:[],
       //表格里的配置
       cloumns:[
         {
           lable:"姓名",
           prop:"username",
           align:"center",
           width:"800"
         },
         {
           lable:"角色",
           prop:"role-name",
           align:"center"
         },
         {
           lable:"电话",
           prop:"mobile",
           align:"center"
         },
         {
           lable:"邮箱",
           prop:"email",
           align:"center"
         },
         {
           lable:"状态",
           prop:"mg_state",
           align:"center",
           slots:"state"
         },
         {
           lable:"操作",
           align:"center"
         }
       ]
     }
   },
   methods: {
     //删除
     delete(scope){
       console.log(scope.row);
     },
     choseedit(scope){
       console.log(scope.row);
     }
   },
   mounted() {

   },
   watch: {

   },
   computed: {

   }
 }
</script>

<style scoped lang='scss'>

</style>
