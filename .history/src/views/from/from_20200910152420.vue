<template>
 <div>
    <jinfrom :dialogVisible.sync="dialogVisible">
        <template v-slot="footer">
            <div>
                
            </div>
        </template>
    </jinfrom>
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