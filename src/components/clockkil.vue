<template>
  <div class="box">
    <el-steps :active="active" finish-status="success" class="jdt">
      <el-step title="步骤 1"></el-step>
      <el-step title="步骤 2"></el-step>
      <el-step title="步骤 3"></el-step>
    </el-steps>
    <div class="con">
      <el-form ref="form" :model="form" label-width="80px">
        <el-form-item label="商品分类:">
          <el-select v-model="form.region" placeholder="请选择">
            <el-option label="服装" value="shanghai"></el-option>
            <el-option label="手机数码" value="beijing"></el-option>
            <el-option label="家用电器" value="shanghai"></el-option>
            <el-option label="家居家装" value="beijing"></el-option>
            <el-option label="汽车用品" value="beijing"></el-option>
          </el-select>
        </el-form-item>
        <el-form-item label="商品名称:">
          <el-input v-model="form.name"></el-input>
        </el-form-item>
        <el-form-item label="副标题:">
          <el-input v-model="form.name"></el-input>
        </el-form-item>
        <el-form-item label="商品品牌:">
          <el-select v-model="form.region" placeholder="请选择品牌">
            <el-option label="小米" value="shanghai"></el-option>
            <el-option label="七匹狼" value="beijing"></el-option>
            <el-option label="海澜之家" value="shanghai"></el-option>
            <el-option label="苹果" value="beijing"></el-option>
            <el-option label="三星" value="beijing"></el-option>
            <el-option label="小米" value="shanghai"></el-option>
            <el-option label="七匹狼" value="beijing"></el-option>
            <el-option label="海澜之家" value="shanghai"></el-option>
            <el-option label="苹果" value="beijing"></el-option>
            <el-option label="三星" value="beijing"></el-option>
          </el-select>
        </el-form-item>
        <el-form-item label="商品货号:">
          <el-input type="textarea" v-model="form.desc"></el-input>
        </el-form-item>
        <el-form-item label="商品售价:">
          <el-input v-model="form.name" placeholder="0"></el-input>
        </el-form-item>
        <el-form-item label="市场价:">
          <el-input v-model="form.name" placeholder="0"></el-input>
        </el-form-item>
        <el-form-item label="商品库存:" placeholder="0">
          <el-input v-model="form.name"></el-input>
        </el-form-item>
        <el-form-item label="计量单位:">
          <el-input v-model="form.name"></el-input>
        </el-form-item>
        <el-form-item label="商品重量:">
          <el-input v-model="form.name" placeholder="0"></el-input>
        </el-form-item>
        <el-form-item label="排序:">
          <el-input v-model="form.name" placeholder="0"></el-input>
        </el-form-item>
      </el-form>
      <el-button style="margin-top: 12px;margin-left: 200px;" @click="next">下一步</el-button>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      active: 0,
      form: {
        name: '',
        region: '',
        date1: '',
        date2: '',
        delivery: false,
        type: [],
        resource: '',
        desc: ''
      }
    }
  },
  methods: {
    next () {
      if (this.active++ > 2) this.active = 0
    },
    onSubmit () {
      console.log('submit!')
    }
  }
}
</script>

<style>
  .box{
    margin-left: 200px;
    width: 800px;
    height: 900px;
    border: 1px darkgrey solid;
  }
  .jdt{
    padding: 20px;
    width: 60%;
    margin-left: 100px;
  }
  .con{
    width: 60%;
    margin-left: 150px;
    margin-top: 30px;
  }
</style>
