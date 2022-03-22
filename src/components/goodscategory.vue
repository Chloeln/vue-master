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
            label="分类名称"
            width="120">
          </el-table-column>
          <el-table-column
            prop="gd"
            label="级别"
            width="80">
          </el-table-column>
          <el-table-column
            prop="tn"
            label="商品数量"
            width="80">
          </el-table-column>
          <el-table-column
            prop="en"
            label="数量单位"
            width="80">
          </el-table-column>
          <el-table-column
            prop="en"
            label="导航栏"
            width="80">
            <el-switch
              v-model="value1">
            </el-switch>
          </el-table-column>
          <el-table-column
            prop="en"
            label="是否显示"
            width="80">
            <el-switch
              v-model="value1">
            </el-switch>
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
        name: 'T恤',
        gd: '一级',
        tn: '200',
        en: '件'
      }, {
        id: '2',
        name: '数码产品',
        gd: '一级',
        tn: '100',
        en: '件'
      }, {
        id: '3',
        name: '配件',
        gd: '一级',
        tn: '200',
        en: '件'
      }, {
        id: '4',
        name: '居家',
        gd: '一级',
        tn: '400',
        en: '件'
      }, {
        id: '5',
        name: '服装',
        gd: '一级',
        tn: '600',
        en: '件'
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
