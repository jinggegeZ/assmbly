<template>
  <div>
    <jinfrom 
    :dialogVisible.sync="dialogVisible"
    @cancel="cancel"
    @ok="ok">
      <template v-slot:footer>
        <div></div>
      </template>
    </jinfrom>
    <el-button @click="dialogVisible=true"></el-button>
  </div>
</template>

<script>
export default {
  name: "",
  props: {},
  components: {},
  data() {
    return {
      dialogVisible: false,
      fromData:[
        {
          type
        }
      ]
    };
  },
  methods: {
    cancel(){
      this.$message.success('点击了取消')
      this.dialogVisible=false
    },
    ok(){
      this.$message.success('点击了确定')
      this.dialogVisible=false
    }
  },
  mounted() {},
  watch: {},
  computed: {},
};
</script>

<style scoped lang='scss'>
</style>