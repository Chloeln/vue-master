<template>
  <div>
	  <div class="top">
      <p><i class="el-icon-search"></i> 筛选搜索</p>
      <div class="content">
        <el-form :inline="true" :model="formInline" class="demo-form-inline">
          <el-form-item label="输入搜索:">
            <el-input v-model="formInline.user" placeholder="订单编号"></el-input>
          </el-form-item>
          <el-form-item label="收货人:" style="margin-left: 20px;">
            <el-input v-model="formInline.user" placeholder="收货人姓名/手机号码"></el-input>
          </el-form-item>
          <el-form-item label="提交时间:" style="margin-left: 20px;">
            <el-col :span="11">
              <el-date-picker type="date" placeholder="选择时间" v-model="sizeForm.date1" style="width: 200px;"></el-date-picker>
            </el-col>
          </el-form-item>
          <br />
          <el-form-item label="订单状态:">
            <el-select v-model="formInline.region" placeholder="全部">
              <el-option label="待付款" value="shanghai"></el-option>
              <el-option label="待发货" value="beijing"></el-option>
              <el-option label="已发货" value="shanghai"></el-option>
              <el-option label="已完成" value="beijing"></el-option>
              <el-option label="已关闭" value="shanghai"></el-option>
            </el-select>
          </el-form-item>
          <el-form-item label="订单分类:">
            <el-select v-model="formInline.region" placeholder="全部">
              <el-option label="正常订单" value="shanghai"></el-option>
              <el-option label="秒杀订单" value="beijing"></el-option>
            </el-select>
          </el-form-item>
          <el-form-item label="订单来源:" style="margin-left: 10px;">
            <el-select v-model="formInline.region" placeholder="全部">
              <el-option label="PC订单" value="shanghai"></el-option>
              <el-option label="APP订单" value="beijing"></el-option>
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
            width="80">
            <template slot-scope="scope">{{ scope.row.id }}</template>
          </el-table-column>
          <el-table-column
            prop=" odn"
            label="订单编号"
            width="180">
            <template slot-scope="scope">{{ scope.row.odn }}</template>
          </el-table-column>
          <el-table-column
            prop="sut"
            label="提交时间"
            width="160">
          </el-table-column>
          <el-table-column
            prop="uid"
            label="用户账号"
            width="80">
          </el-table-column>
          <el-table-column
            prop="orm"
            label="订单金额"
            width="80">
          </el-table-column>
          <el-table-column
            prop="payw"
            label="支付方式"
            width="80">
          </el-table-column>
          <el-table-column
            prop="odero"
            label="订单来源"
            width="80">
          </el-table-column>
          <el-table-column
            prop="status"
            label="订单状态"
            width="80">
          </el-table-column>
          <el-table-column
            prop="option"
            label="操作"
            show-overflow-tooltip>
            <el-button>查看订单</el-button>
            <el-button type="danger">删除订单</el-button>
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
      sizeForm: {
        name: '',
        region: '',
        date1: '',
        date2: '',
        delivery: false,
        type: [],
        resource: '',
        desc: ''
      },
      tableData: [{
        id: '12',
        odn: '2018091501010000001',
        sut: '2018-09-15 12:24:27',
        uid: 'test',
        orm: '￥18732',
        payw: '未支付',
        odero: 'APP订单',
        status: '已关闭'
      }, {
        id: '14',
        odn: '2018091501010000002',
        sut: '2018-09-15 12:24:27',
        uid: 'test',
        orm: '￥18732',
        payw: '未支付',
        odero: 'APP订单',
        status: '已关闭'
      }, {
        id: '15',
        odn: '2018091501010000003',
        sut: '2018-09-15 12:24:27',
        uid: 'test',
        orm: '￥18732',
        payw: '未支付',
        odero: 'APP订单',
        status: '已关闭'
      }, {
        id: '16',
        odn: '2018091501010000004',
        sut: '2018-09-15 12:24:27',
        uid: 'test',
        orm: '￥18732',
        payw: '未支付',
        odero: 'APP订单',
        status: '已关闭'
      }, {
        id: '17',
        odn: '2018091501010000005',
        sut: '2018-09-15 12:24:27',
        uid: 'test',
        orm: '￥18732',
        payw: '未支付',
        odero: 'APP订单',
        status: '已关闭'
      }, {
        id: '14',
        odn: '2018091501010000002',
        sut: '2018-09-15 12:24:27',
        uid: 'test',
        orm: '￥18732',
        payw: '未支付',
        odero: 'APP订单',
        status: '已关闭'
      }, {
        id: '15',
        odn: '2018091501010000003',
        sut: '2018-09-15 12:24:27',
        uid: 'test',
        orm: '￥18732',
        payw: '未支付',
        odero: 'APP订单',
        status: '已关闭'
      }, {
        id: '16',
        odn: '2018091501010000004',
        sut: '2018-09-15 12:24:27',
        uid: 'test',
        orm: '￥18732',
        payw: '未支付',
        odero: 'APP订单',
        status: '已关闭'
      }, {
        id: '17',
        odn: '2018091501010000005',
        sut: '2018-09-15 12:24:27',
        uid: 'test',
        orm: '￥18732',
        payw: '未支付',
        odero: 'APP订单',
        status: '已关闭'
      }, {
        id: '14',
        odn: '2018091501010000002',
        sut: '2018-09-15 12:24:27',
        uid: 'test',
        orm: '￥18732',
        payw: '未支付',
        odero: 'APP订单',
        status: '已关闭'
      }, {
        id: '15',
        odn: '2018091501010000003',
        sut: '2018-09-15 12:24:27',
        uid: 'test',
        orm: '￥18732',
        payw: '未支付',
        odero: 'APP订单',
        status: '已关闭'
      }, {
        id: '16',
        odn: '2018091501010000004',
        sut: '2018-09-15 12:24:27',
        uid: 'test',
        orm: '￥18732',
        payw: '未支付',
        odero: 'APP订单',
        status: '已关闭'
      }, {
        id: '17',
        odn: '2018091501010000005',
        sut: '2018-09-15 12:24:27',
        uid: 'test',
        orm: '￥18732',
        payw: '未支付',
        odero: 'APP订单',
        status: '已关闭'
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
