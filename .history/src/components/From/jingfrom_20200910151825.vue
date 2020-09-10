<template>
 <div>
    <el-dialog
  title="提示"
  :visible.sync="dialogVisible"
  width="30%"
  :before-close="handleClose">
  <el-form>
    <el-form-item label="用户名"></el-form-item>
  </el-form>
  <span slot="footer">
    <el-button @click="dialogVisible = false">取 消</el-button>
    <el-button type="primary" @click="dialogVisible = false">确 定</el-button>
  </span>
</el-dialog>
 </div>
</template>

<script>
 export default {
   name: '',
   props: {
       dialogVisible:{
           type:Boolean,
           default:false
       }
   },
   components: {

   },
   data () {
     return {

     }
   },
   methods: {
       handleClose(){
           this.$emit('update:dialogVisible',false)
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