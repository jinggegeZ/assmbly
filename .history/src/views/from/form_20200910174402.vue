<template>
  <div>
    <jing-from :dialogVisible.sync="dialogVisible" :fromData="fromData" @cancel="cancel" @ok="ok">
      <template v-slot:footer>
        <div>这是一个底部</div>
      </template>
      
    </jing-from>
     <el-button @click="dialogVisible=true" type="primary">点击打开</el-button>
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
      fromData: [
        {
          label: "用户名",
          //代表表单元素类型
          type: "input",
          // v-model绑定的值
          value: "",
          rule:[],
          attrs: {
            placeholder: "请输入用户名",
            clearable: true,
          },
        },
        {
          label: "密码",
          //代表表单元素类型
          type: "input",
          // v-model绑定的值
          value: "",
          attrs: {
            placeholder: "请输入密码",
            clearable: true,
            "show-password": true,
          },
        },
        {
          label: "分配角色",
          //代表表单元素类型
          type: "select",
          // v-model绑定的值
          value: "",
          children: [
            {
              type: "option",
              value: "选项1",
              label: "黄金奶",
            },
            {
              type: "option",
              value: "选项2",
              label: "双皮奶",
            },
            {
              type: "option",
              value: "选项3",
              label: "臭豆腐",
            },
          ],
        },
      ],
    };
  },
  methods: {
    cancel() {
      this.$message.success("点击了取消");
      this.dialogVisible = false;
    },
    ok() {
      this.$message.success("点击了确定");
      this.dialogVisible = false;
    },
  },
  mounted() {},
  watch: {},
  computed: {},
};
</script>

<style scoped lang='scss'>
</style>