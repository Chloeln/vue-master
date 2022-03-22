<template>
  <div>
	  <div class="top">
      <p><i class="el-icon-search"></i> 筛选搜索</p>
      <div class="content">
        <el-form :inline="true" :model="formInline" class="demo-form-inline">
          <el-form-item label="输入搜索:">
            <el-input v-model="formInline.user" placeholder="输入搜索"></el-input>
          </el-form-item>
          <el-form-item label="商品货号:" style="margin-left: 20px;">
            <el-input v-model="formInline.user" placeholder="商品货号"></el-input>
          </el-form-item>
          <el-form-item label="商品分类:" style="margin-left: 20px;">
            <el-select v-model="formInline.region" placeholder="请选择">
              <el-option label="服装" value="shanghai"></el-option>
              <el-option label="手机数码" value="beijing"></el-option>
              <el-option label="家用电器" value="shanghai"></el-option>
              <el-option label="家居家装" value="beijing"></el-option>
            </el-select>
          </el-form-item>
          <br />
          <el-form-item label="商品品牌:">
            <el-select v-model="formInline.region" placeholder="请选择品牌">
              <el-option label="小米" value="shanghai"></el-option>
              <el-option label="七匹狼" value="beijing"></el-option>
              <el-option label="海澜之家" value="shanghai"></el-option>
              <el-option label="苹果" value="beijing"></el-option>
              <el-option label="三星" value="shanghai"></el-option>
              <el-option label="华为" value="beijing"></el-option>
            </el-select>
          </el-form-item>
          <el-form-item label="上架状态:">
            <el-select v-model="formInline.region" placeholder="全部">
              <el-option label="上架" value="shanghai"></el-option>
              <el-option label="下架" value="beijing"></el-option>
            </el-select>
          </el-form-item>
          <el-form-item label="审核状态:" style="margin-left: 10px;">
            <el-select v-model="formInline.region" placeholder="全部">
              <el-option label="审核通过" value="shanghai"></el-option>
              <el-option label="未审核" value="beijing"></el-option>
            </el-select>
          </el-form-item>
          <el-form-item class="button" style="margin-right: 40px;margin-top: -120px;">
            <el-button>重置</el-button>
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
            prop="pic"
            label="商品图片"
            width="100">
            <template slot-scope="scope">
              <img :src="scope.row.pic" min-width="70" height="70"/>
            </template>
          </el-table-column>
          <el-table-column
            prop="name"
            label="商品名称"
            width="260">
          </el-table-column>
          <el-table-column
            prop="address"
            label="价格/货号"
            width="122">
          </el-table-column>
          <el-table-column
            prop="lable"
            label="标签"
            width="120">
            <el-switch
              v-model="value1"
              inactive-text="上架:">
            </el-switch>
            <br />
            <el-switch
              v-model="value1"
              inactive-text="新品:">
            </el-switch>
            <br />
            <el-switch
              v-model="value1"
              inactive-text="推荐:">
            </el-switch>
          </el-table-column>
          <el-table-column
            prop="sort"
            label="排序"
            width="80">
          </el-table-column>
          <el-table-column
            prop="sales"
            label="销量"
            width="80">
          </el-table-column>
          <el-table-column
            prop="status"
            label="审核状态"
            width="120">
          </el-table-column>
          <el-table-column
            prop="option"
            label="操作"
            show-overflow-tooltip>
            <el-button>查看</el-button>
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
        id: '26',
        pic: 'https://img2.baidu.com/it/u=281984195,4221424401&fm=26&fmt=auto',
        name: '华为 HUAWEI P20 品牌：华为',
        address: '价格：￥2699 货号：7437788',
        sort: '100',
        sales: '0',
        status: '未审核'
      }, {
        id: '27',
        pic: 'https://img2.baidu.com/it/u=281984195,4221424401&fm=26&fmt=auto',
        name: '小米8 全面屏游戏智能手机 6GB+64GB 黑色 全网通4G 双卡双待 品牌：小米',
        address: '价格：￥3788 货号：6946605',
        sort: '100',
        sales: '0',
        status: '未审核'
      }, {
        id: '28',
        pic: 'https://img2.baidu.com/it/u=281984195,4221424401&fm=26&fmt=auto',
        name: '小米 红米5A 全网通版 3GB+32GB 香槟金 移动联通电信4G手机 双卡双待 品牌：小米',
        address: '价格：￥2699 货号：7437788',
        sort: '100',
        sales: '0',
        status: '未审核'
      }, {
        id: '29',
        pic: 'https://img2.baidu.com/it/u=281984195,4221424401&fm=26&fmt=auto',
        name: 'Apple iPhone 8 Plus 64GB 红色特别版 移动联通电信4G手机 品牌：苹果',
        address: '价格：￥2699 货号：7437788',
        sort: '100',
        sales: '0',
        status: '未审核'
      }, {
        id: '30',
        pic: 'https://img2.baidu.com/it/u=281984195,4221424401&fm=26&fmt=auto',
        name: 'HLA海澜之家简约动物印花短袖T恤 品牌：海澜之家',
        address: '价格：￥2699 货号：7437788',
        sort: '100',
        sales: '0',
        status: '未审核'
      }],
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
    height: 180px;
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
