<template>
 <div>
    <el-dialog
  title="提示"
  :visible.sync="dialogVisible"
  width="30%"
  :before-close="handleClose">
  <el-form>
    <el-form-item label="用户名" prop="username">
        <el-input placeholder="请输入用户名"></el-input>
    </el-form-item>
  </el-form>
  <!-- <span slot="footer">
    <el-button @click="cancel">取 消</el-button>
    <el-button type="primary" @click="ok">确 定</el-button>
  </span> -->
    <slot name="footer"><slot>
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
       //关闭Diolog
       handleClose(){
           this.$emit('update:dialogVisible',false)
       },
       //点击取消
       cancel(){},
       //点击确定
       OK(){}
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