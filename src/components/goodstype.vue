<template>
  <div>
    <div class="center">
      <div>
        <p>
          <i class="el-icon-search"></i> 数据列表
          <el-button style="margin-left:1000px;">添加</el-button>
        </p>
      </div>
    </div>
    <div class="bottom">
        <el-table
          v-loading:loading
          ref="multipleTable"
          :data="tableData"
          tooltip-effect="dark"
          border
          style="width: 100%"
          @selection-change="handleSelectionChange">
          <el-table-column
            type="selection"
            width="100">
          </el-table-column>
          <el-table-column
            label="编号"
            width="100">
            <template slot-scope="scope">{{ scope.row.id }}</template>
          </el-table-column>
          <el-table-column
            prop="name"
            label="类型名称"
            width="250">
          </el-table-column>
          <el-table-column
            prop="tn"
            label="属性数量"
            width="122">
          </el-table-column>
          <el-table-column
            prop="en"
            label="参数数量"
            width="80">
          </el-table-column>
          <el-table-column
            prop="set"
            label="设置"
            width="300">
            <el-button>属性列表</el-button>
            <el-button>参数列表</el-button>
          </el-table-column>
          <el-table-column
            prop="option"
            label="操作"
            show-overflow-tooltip>
            <el-button>编辑</el-button>
            <el-button type="danger">删除</el-button>
          </el-table-column>
        </el-table>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      value1: true,
      value2: true,
      formInline: {
        user: '',
        region: ''
      },
      tableData: [{
        id: '1',
        name: '服装 T恤',
        tn: '2',
        en: '5'
      }, {
        id: '2',
        name: '数码产品',
        tn: '1',
        en: '5'
      }, {
        id: '3',
        name: '配件',
        tn: '2',
        en: '1'
      }, {
        id: '4',
        name: '居家',
        tn: '4',
        en: '7'
      }, {
        id: '5',
        name: '服装 裤装',
        tn: '6',
        en: '4'
      }
      ],
      multipleSelection: []
    }
  },
  methods: {
    onSubmit () {
      console.log('submit!')
    },
    toggleSelection (rows) {
      if (rows) {
        rows.forEach(row => {
          this.$refs.multipleTable.toggleRowSelection(row)
        })
      } else {
        this.$refs.multipleTable.clearSelection()
      }
    },
    handleSelectionChange (val) {
      this.multipleSelection = val
    }
  }
}
</script>

<style>

  .content{
    padding: 10px;
    margin-left: 50px;
  }
  .center{
    margin-top: 20px;
    padding-left: 10px;
    padding-bottom: 20px;
    padding-right: 10px;
    margin-left: 20px;
    height: 40px;
    width: 96%;
    border: 1px solid lightgrey;
  }
  .bottom{
    margin-top: 20px;
    width: 96%;
    border: 1px solid lightgrey;
    margin-left: 20px;
  }
</style>
