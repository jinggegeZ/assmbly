<template>
  <div>
    <el-table :data="tableData" v-loading="!tableData.length">
      <template v-for="(item,index) in cloumns">
        <el-table-cloumn
          v-if="item.prop"
          :lable="item.lable"
          :prop="item.prop"
          :align="item.align"
          :width="item.width"
          :key="index">
          <template slot-scope="scope">
           <slot v-if="item.slots"></slot>
         </template>
          </el-table-cloumn>
        <el-table-cloumn
          v-else
          :key="index"
          :lable="item.lable"
          :align="item.align"
          :width="item.width"
        >
          <template slot-scope="scope">
            <slot name="action" :scope="scope"></slot>
          </template>
        </el-table-cloumn>
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