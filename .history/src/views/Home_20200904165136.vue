<template>
 <div>
  <jing-table :tableData="tableData" :cloumns="cloumns"></jing-table>
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
           prop:"username"
         },
         {
           lable:"角色",
           prop:"role-name"
         },
         {
           lable:"电话",
           prop:"mobile"
         },
         {
           lable:"邮箱",
           prop:"email"
         },
         {
           lable:"状态",
           prop:"mg_state"
         }
       ]
     }
   },
   methods: {

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
