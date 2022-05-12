<template>
  <div class="footer-container">
    <el-row>
      <el-col :span="12" class="el-icon-truck current">
        <div class="grid-content bg-purple">{{ t1 }}</div></el-col
      >
      <el-col :span="12" class="el-icon-user-solid">
        <div class="grid-content bg-purple-light">{{ t2 }}</div></el-col
      >
    </el-row>
  </div>
</template>

<script>
export default {
  props: {
    t1: {
      type: String,
      default: "首页",
    },
    t2: {
      type: String,
      default: "我的",
    },
    data() {
      return {
        isCurrent:true,
      };
    },
    methods: {
        
    },
  },
};
</script>

<style lang="less" scoped>
.footer-container {
  position: absolute;
  left: 0px;
  top: 764px;
  width: 390px;
  height: 80px;
  line-height: 20px;
  text-align: center;
  background-color: white;
  .el-icon-truck,
  .el-icon-user-solid {
    margin-top: 20px;
    margin-bottom: 20px;
    line-height: 20px;
    text-align: center;
  }
}
.current {
  color: #3894ff;
}
</style>