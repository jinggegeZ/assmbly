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
           align:"center"
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
