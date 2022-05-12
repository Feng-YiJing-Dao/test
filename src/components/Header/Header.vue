<template>
  <div class="header-container">
    <div class="title">
      <span class="el-icon-arrow-left"></span>
      <span>{{ title }}</span>
    </div>
    <img class="topPic" src="@/assets/img.jpeg" alt="车图" />  
    <!-- <el-image :src="src" lazy></el-image> -->
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: "泉运拼车",
    },
  },
  data() {
    return {
      src: "@/assets/img.jpeg",
    };
  },
};
</script>

<style lang="less" scoped>
.header-container {
  background-color: #f8f8f8;
  padding: 0px;
  margin: 0px;
  left: -10px;
  top: 44px;
  width: 390px;
  height: 44px;
  color: rgba(16, 16, 16, 100);
  font-size: 18px;
  text-align: center;
  line-height: 44px;
  font-family: PingFang SC;
  .el-icon-arrow-left {
    position: absolute;
    left: 12px;
    top: 12px;
    width: 32px;
    height: 32px;
    // background-color: rgba(204, 204, 204, 100);
  }
  .topPic {
    position: absolute;
    left: 0px;
    top: 44px;
    width: 390px;
    height: 100px;
  }
}
</style>
