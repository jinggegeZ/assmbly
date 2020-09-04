<template>
  <div>
    <el-table :data="tableData" v-loading="!tableData.length">
      <template v-for="(item,index) in cloumns">
        <el-table-cloumn
          :lable="item.lable"
          :prop="item.prop"
          :align="item.align"
          :width="item.width"
          :key="index"
        ></el-table-cloumn>
      </template>
    </el-table>
  </div>
</template>

<script>
export default {
  name: "",
  props: {
    tableData: {
      type: Array,
      required: true,
    },
    cloumns: {
      type: Array,
      required: true,
    },
  },
  components: {},
  data() {
    return {};
  },
  methods: {},
  mounted() {},
  watch: {},
  computed: {},
};
</script>

<style scoped lang='scss'>
</style>