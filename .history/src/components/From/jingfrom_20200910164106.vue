<template>
  <div>
    <el-dialog title="提示" :visible.sync="dialogVisible" width="30%" :before-close="handleClose">
      <el-form>
        <el-form-item :label="item.label" v-for="(item,index) in fromData" :key="index">
          <component :is="`el-${item.type}`" v-bind="item.attrs" v-if="!item.children"></component>
          <component :is="`el-${item.type}`" v-bind="item.attrs" v-if="item.children"></component>
        </el-form-item>
      </el-form>
    <template>
    <slot name="footer" v-if="$slots.footer"><slot>
    <span slot="footer" v-if="!$slots.footer">
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
    fromData:{
      type:Array,
      required:true
    }
  },
  components: {},
  data() {
    return {};
  },
  methods: {
    //关闭Diolog
    handleClose() {
      this.$emit("update:dialogVisible", false);
    },
    //点击取消
    cancel() {
      this.$emit('cancel')
    },
    //点击确定
    OK() {
      this.$emit('ok')
    },
  },
  mounted() {
    console.log(this.$slots);
  },
  watch: {},
  computed: {},
};
</script>

<style scoped lang='scss'>
</style>