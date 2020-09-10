<template>
  <div>
    <jinfrom 
    :dialogVisible.sync="dialogVisible"
    :fo
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
          label:'用户名',
          //代表表单元素类型
          type:"input",
          // v-model绑定的值
          value:''
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