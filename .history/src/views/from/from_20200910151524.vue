<template>
 <div>
    <jinfrom :dialogVisible.sync="dialogVisible"></jinfrom>
    <el-button @click="dialogVisible=true"></el-button>
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
         dialogVisible:false
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