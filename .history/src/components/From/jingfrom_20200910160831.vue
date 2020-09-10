<template>
  <div>
    
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
       console.log(this.$slots);
   },
   watch: {

   },
   computed: {

   }
 }
</script>

<style scoped lang='scss'>

</style>