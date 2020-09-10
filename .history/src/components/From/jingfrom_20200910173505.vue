<template>
  <div>
    <el-dialog title="提示" :visible.sync="dialogVisible" width="30%" :before-close="handleClose">
      <el-form>
        <template v-for="(item,index) in fromData">
          <el-form-item  :label="item.label" :key="index" v-if="!item.children">
            <component v-model="value" :is="`el-${item.type}`" v-bind="item.attrs"></component>
          </el-form-item>
          <el-form-item :label="item.label" :key="index" v-if="item.children">
            <component v-model="value" :is="`el-${item.type}`" v-bind="item.attrs">
              <component 
                v-for="(child,idx) in item.children"
                v-model="item.value"
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
      value:''
    };
  },
  methods: {
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
    console.log(this.$slots);
  },
  watch: {},
  computed: {},
};
</script>

<style scoped lang='scss'>
</style>