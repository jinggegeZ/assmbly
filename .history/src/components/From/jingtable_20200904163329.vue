<template>
 <div>
    <el-table :data="tableData" v-loading="!tableData.length">
        el-table-cloumn
    </el-table>
 </div>
</template>

<script>
 export default {
   name: '',
   props: {
       tableData:{
           type:Array,
           required:true
       },
       cloumns:{
           type:Array,
           required:true
       }
   },
   components: {

   },
   data () {
     return {

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