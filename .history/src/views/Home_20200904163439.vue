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
           lable:''
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
