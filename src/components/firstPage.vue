<template>
  <div style="width: 100%; height: 100%;">
        <el-main>
          <template>
            <router-view></router-view>
          </template>
          <div class="app-container">
              <div class="address-layout">
                <el-row :gutter="20">
                  <el-col :span="6">
                    <div class="out-border">
                      <div class="layout-title">后台项目</div>
                      <div class="color-main address-content">
                        <a href="#">mall</a>
                      </div>
                    </div>
                  </el-col>
                  <el-col :span="6">
                    <div class="out-border">
                      <div class="layout-title">前端项目</div>
                      <div class="color-main address-content">
                        <a href="#">mall-admin-web</a>
                      </div>
                    </div>
                  </el-col>
                  <el-col :span="6">
                    <div class="out-border">
                      <div class="layout-title">学习教程</div>
                      <div class="color-main address-content">
                        <a href="#">mall-learning</a>
                      </div>
                    </div>
                  </el-col>
                </el-row>
              </div>
              <div class="total-layout">
                <el-row :gutter="20">
                  <el-col :span="6">
                    <div class="total-frame">
                      <img src="../img_home_order.png" class="total-icon">
                      <div class="total-title">今日订单总数</div>
                      <div class="total-value">￥200</div>
                    </div>
                  </el-col>
                  <el-col :span="6">
                    <div class="total-frame">
                      <img src="../img_home_today_amount.png" class="total-icon">
                      <div class="total-title">今日销售总额</div>
                      <div class="total-value">￥5000.00</div>
                    </div>
                  </el-col>
                  <el-col :span="6">
                    <div class="total-frame">
                      <img src="../img_home_yesterday_amount.png" class="total-icon">
                      <div class="total-title">昨日销售总额</div>
                      <div class="total-value">￥5000.00</div>
                    </div>
                  </el-col>
                </el-row>
              </div>
              <el-card class="mine-layout">
                <div style="text-align: center">
                  <img width="150px" height="150px" src="http://macro-oss.oss-cn-shenzhen.aliyuncs.com/mall/banner/qrcode_for_macrozheng_258.jpg">
                </div>
                <div style="text-align: center">mall全套学习教程连载中！</div>
                <div style="text-align: center;margin-top: 5px"><span class="color-main">关注公号</span>，第一时间获取。</div>
              </el-card>
              <div class="un-handle-layout">
                <div class="layout-title">待处理事务</div>
                <div class="un-handle-content">
                  <el-row :gutter="20">
                    <el-col :span="8">
                      <div class="un-handle-item">
                        <span class="font-medium">待付款订单</span>
                        <span style="float: right" class="color-danger">(10)</span>
                      </div>
                    </el-col>
                    <el-col :span="8">
                      <div class="un-handle-item">
                        <span class="font-medium">已完成订单</span>
                        <span style="float: right" class="color-danger">(10)</span>
                      </div>
                    </el-col>
                    <el-col :span="8">
                      <div class="un-handle-item">
                        <span class="font-medium">待确认收货订单</span>
                        <span style="float: right" class="color-danger">(10)</span>
                      </div>
                    </el-col>
                  </el-row>
                  <el-row :gutter="20">
                    <el-col :span="8">
                      <div class="un-handle-item">
                        <span class="font-medium">待发货订单</span>
                        <span style="float: right" class="color-danger">(10)</span>
                      </div>
                    </el-col>
                    <el-col :span="8">
                      <div class="un-handle-item">
                        <span class="font-medium">新缺货登记</span>
                        <span style="float: right" class="color-danger">(10)</span>
                      </div>
                    </el-col>
                    <el-col :span="8">
                      <div class="un-handle-item">
                        <span class="font-medium">待处理退款申请</span>
                        <span style="float: right" class="color-danger">(10)</span>
                      </div>
                    </el-col>
                  </el-row>
                  <el-row :gutter="20">
                    <el-col :span="8">
                      <div class="un-handle-item">
                        <span class="font-medium">已发货订单</span>
                        <span style="float: right" class="color-danger">(10)</span>
                      </div>
                    </el-col>
                    <el-col :span="8">
                      <div class="un-handle-item">
                        <span class="font-medium">待处理退货订单</span>
                        <span style="float: right" class="color-danger">(10)</span>
                      </div>
                    </el-col>
                    <el-col :span="8">
                      <div class="un-handle-item">
                        <span class="font-medium">广告位即将到期</span>
                        <span style="float: right" class="color-danger">(10)</span>
                      </div>
                    </el-col>
                  </el-row>
                </div>
              </div>
              <div class="overview-layout">
                <el-row :gutter="20">
                  <el-col :span="12">
                    <div class="out-border">
                      <div class="layout-title">商品总览</div>
                      <div style="padding: 40px">
                        <el-row>
                          <el-col :span="6" class="color-danger overview-item-value">100</el-col>
                          <el-col :span="6" class="color-danger overview-item-value">400</el-col>
                          <el-col :span="6" class="color-danger overview-item-value">50</el-col>
                          <el-col :span="6" class="color-danger overview-item-value">500</el-col>
                        </el-row>
                        <el-row class="font-medium">
                          <el-col :span="6" class="overview-item-title">已下架</el-col>
                          <el-col :span="6" class="overview-item-title">已上架</el-col>
                          <el-col :span="6" class="overview-item-title">库存紧张</el-col>
                          <el-col :span="6" class="overview-item-title">全部商品</el-col>
                        </el-row>
                      </div>
                    </div>
                  </el-col>
                  <el-col :span="12">
                    <div class="out-border">
                      <div class="layout-title">用户总览</div>
                      <div style="padding: 40px">
                        <el-row>
                          <el-col :span="6" class="color-danger overview-item-value">100</el-col>
                          <el-col :span="6" class="color-danger overview-item-value">200</el-col>
                          <el-col :span="6" class="color-danger overview-item-value">1000</el-col>
                          <el-col :span="6" class="color-danger overview-item-value">5000</el-col>
                        </el-row>
                        <el-row class="font-medium">
                          <el-col :span="6" class="overview-item-title">今日新增</el-col>
                          <el-col :span="6" class="overview-item-title">昨日新增</el-col>
                          <el-col :span="6" class="overview-item-title">本月新增</el-col>
                          <el-col :span="6" class="overview-item-title">会员总数</el-col>
                        </el-row>
                      </div>
                    </div>
                  </el-col>
                </el-row>
              </div>
            </div>
            <img src="../折线图.png" style="width: 83%; margin-left: 110px;" />
        </el-main>
  </div>
</template>

<script>
</script>

<style scoped>
html
{
  overflow-y: scroll;
}
a{
  text-decoration: none;
}
.el-header {
  background-color: #B3C0D1;
  color: #333;
  line-height: 60px;
}
.el-aside {
  color: #333;
}
.el-row {
  margin-bottom: 20px;
  &:last-child {
    margin-bottom: 30px;
  }
}
.row-bg {
  padding: 10px 0;
  background-color: #f9fafc;
}
.app-container {
  margin-top: 40px;
  margin-left: 120px;
  margin-right: 120px;
}
.address-layout {
}
.total-layout {
  margin-top: 20px;
}
.total-frame {
  border: 1px solid #DCDFE6;
  padding: 20px;
  height: 100px;
}
.total-icon {
  color: #409EFF;
  width: 60px;
  height: 60px;
}
.total-title {
  position: relative;
  font-size: 16px;
  color: #909399;
  left: 70px;
  top: -50px;
}
.total-value {
  position: relative;
  font-size: 18px;
  color: #606266;
  left: 70px;
  top: -40px;
}
.un-handle-layout {
  margin-top: 20px;
  border: 1px solid #DCDFE6;
}
.layout-title {
  color: #606266;
  padding: 15px 20px;
  background: #F2F6FC;
  font-weight: bold;
}
.un-handle-content {
  padding: 20px 40px;
}
.un-handle-item {
  border-bottom: 1px solid #EBEEF5;
  padding: 10px;
}
.overview-layout {
  margin-top: 20px;
}
.overview-item-value {
  font-size: 24px;
  text-align: center;
}
.overview-item-title {
  margin-top: 10px;
  text-align: center;
}
.out-border {
  border: 1px solid #DCDFE6;
}
.statistics-layout {
  margin-top: 20px;
  border: 1px solid #DCDFE6;
}
.mine-layout {
  position: absolute;
  right: 150px;
  top: 150px;
  width: 250px;
  height: 235px;
}
.address-content{
  padding: 20px;
  font-size: 18px
}
.color-danger{
  color: red;
}
</style>
