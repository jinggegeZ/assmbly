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
          :key="index"
        >
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
    <div v-if="showPagination" class="pagination">
      <el-pagination
        @size-change="handleSizeChange"
        @current-change="handleCurrentChange"
        :current-page="currentPage"
        :page-sizes="pageSizes"
        :page-size="pageSize"
        layout="total, sizes, prev, pager, next, jumper"
        :total="400"
      ></el-pagination>
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
    total:{
      type:[String,Number]
    },
    showPagination:{
      type:Boolean,
      default:true
    },
    currentPage:{
      type:Number,
      default:1
    },
    pageSizes:{
      type: Array,
      default:() => [10,20,30,40]
    },
    pageSize:{
       type:Number,
        default:10
    }
  },
  components: {},
  data() {
    return {
      currentPage:1
    };
  },
  methods: {
    handleSizeChange(val) {
        this.$emit('handleSizeChange', val)
      },
    handleCurrentChange(val) {
        this.$emit('handleCurrentChange', val)
      },
  
  },
  mounted() {},
  watch: {},
  computed: {},
};
</script>

<style scoped lang='scss'>
.pagination {
  display: flex;
  margin-top: 26px;
  width: 100%;
  justify-content: flex-start;
  position: relative;
  left: 50px;
}
</style>