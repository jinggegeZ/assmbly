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
           <slot v-if="item.slots" :name="item.slots" :scope="scope"></slot>
           <template v-else>{{scope.row[item.prop]}}</template>>
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
     <div v-if="showpage">
        <el-pagination
      @size-change="handleSizeChange"
      @current-change="handleCurrentChange"
      :current-page="currentPage"
      :page-sizes="[100, 200, 300, 400]"
      :page-size="100"
      layout="total, sizes, prev, pager, next, jumper"
      :total="400">
    </el-pagination>
     </div>
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
    return {
      currentPage:1
    };
  },
  methods: {
      handleSizeChange(val) {
        console.log(`每页 ${val} 条`);
      },
      handleCurrentChange(val) {
        console.log(`当前页: ${val}`);
      }
  },
  mounted() {},
  watch: {},
  computed: {},
};
</script>

<style scoped lang='scss'>
</style>