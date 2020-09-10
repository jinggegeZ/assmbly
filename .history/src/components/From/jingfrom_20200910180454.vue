<template>
  <div>
    <el-dialog title="提示" :visible.sync="dialogVisible" width="30%" :before-close="handleClose">
      <el-form :model="formOptions" :rules="rules">
        <template v-for="(item,index) in fromData">
          <el-form-item :label="item.label" :key="index" :prop="item.prop" v-if="!item.children">
            <component :is="`el-${item.type}`" v-model="formOptions(item.prop)" v-bind="item.attrs"></component>
          </el-form-item>
          <el-form-item :label="item.label" :key="index" v-if="item.children">
            <component v-model="item.value" :is="`el-${item.type}`" v-bind="item.attrs">
              <component
                v-for="(child,idx) in item.children"
                :key="idx"
                :is="`el-${child.type}`"
                :label="child.label"
                :value="child.value"
              ></component>
            </component>
          </el-form-item>
        </template>
      </el-form>
      <template>
        <slot name="footer" v-if="$slots.footer"></slot>
        <span slot="footer" v-else>
          <el-button @click="cancel">取 消</el-button>
          <el-button type="primary" @click="ok">确 定</el-button>
        </span>
      </template>
    </el-dialog>
  </div>
</template>
<script>
export default {
  name: "",
  props: {
    dialogVisible: {
      type: Boolean,
      default: false,
    },
    fromData: {
      type: Array,
      required: true,
    },
  },
  components: {},
  data() {
    return {
      formOptions: {},
      rules: {},
    };
  },
  methods: {
    //初始化数据
    setInitvale(){
      let options = {};
    let rules = {};
    this.fromData.map((item) => {
      rules[item.prop] = item.rules;
      options[item.prop] = item.value;
    });
    this.formOptions = JSON.parse(JSON.stringify(options));
    this.rules = JSON.parse(JSON.stringify(rules));
    },
    //关闭Diolog
    handleClose() {
      this.$emit("update:dialogVisible", false);
    },
    //点击取消
    cancel() {
      this.$emit("cancel");
    },
    //点击确定
    OK() {
      this.$emit("ok");
    },
  },
  mounted() {
    this.setInitvale()
  },
  watch: {
    fromData(){
       this.setInitvale()
    }
  },
  computed: {},
};
</script>

<style scoped lang='scss'>
</style>