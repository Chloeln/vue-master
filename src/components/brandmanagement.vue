<template>
  <div>
	  <div class="top">
      <p><i class="el-icon-search"></i> 筛选搜索</p>
      <div class="content">
        <el-form :inline="true" :model="formInline" class="demo-form-inline">
          <el-form-item label="输入搜索:">
            <el-input v-model="formInline.user" placeholder="品牌名称/关键字"></el-input>
          </el-form-item>
          <el-form-item class="button" style="margin-left: 700px;margin-top: -40px;">
            <el-button type="primary">查询结果</el-button>
          </el-form-item>
        </el-form>
      </div>
	  </div>
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
            label="商品名称"
            width="250">
          </el-table-column>
          <el-table-column
            prop="firstword"
            label="品牌首字母"
            width="122">
          </el-table-column>
          <el-table-column
            prop="sort"
            label="排序"
            width="80">
          </el-table-column>
          <el-table-column
            prop="sales"
            label="是否显示"
            width="80">
          </el-table-column>
          <el-table-column
            prop="about"
            label="相关"
            width="200">
          </el-table-column>
          <el-table-column
            prop="option"
            label="操作"
            show-overflow-tooltip>
            <el-button>编辑</el-button>
            <el-button type="danger">删除</el-button>
          </el-table-column>
        </el-table>
        <div style="margin-top: 20px">
          <el-button @click="toggleSelection([tableData[1], tableData[2]])">切换第二、第三行的选中状态</el-button>
          <el-button @click="toggleSelection()">取消选择</el-button>
        </div>
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
        id: '6',
        name: '小米',
        firstword: 'S',
        sort: '500',
        sales: '0',
        about: '商品:100 评价:1000'
      }, {
        id: '49',
        name: '苹果',
        firstword: 'M',
        sort: '200',
        sales: '0',
        about: '商品:100 评价:1000'
      }, {
        id: '28',
        name: '海澜之家',
        firstword: 'S',
        sort: '100',
        sales: '0',
        about: '商品:100 评价:1000'
      }, {
        id: '51',
        name: '三星',
        firstword: 'S',
        sort: '700',
        sales: '0',
        about: '商品:100 评价:1000'
      }, {
        id: '30',
        name: '华为',
        firstword: 'S',
        sort: '400',
        sales: '0',
        about: '商品:100 评价:1000'
      }, {
        id: '49',
        name: '苹果',
        firstword: 'M',
        sort: '200',
        sales: '0',
        about: '商品:100 评价:1000'
      }, {
        id: '28',
        name: '海澜之家',
        firstword: 'S',
        sort: '100',
        sales: '0',
        about: '商品:100 评价:1000'
      }, {
        id: '51',
        name: '三星',
        firstword: 'S',
        sort: '700',
        sales: '0',
        about: '商品:100 评价:1000'
      }, {
        id: '30',
        name: '华为',
        firstword: 'S',
        sort: '400',
        sales: '0',
        about: '商品:100 评价:1000'
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
  .top{
    padding: 10px;
    margin-left: 20px;
    height: 120px;
    width: 96%;
    border: 1px solid lightgrey;
  }
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
