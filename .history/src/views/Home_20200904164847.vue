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
           prop:"username"
         },
         {
           lable:"姓名",
           prop:"username"
         },
         {
           lable:"姓名",
           prop:"username"
         },
         {
           lable:"姓名",
           prop:"username"
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
