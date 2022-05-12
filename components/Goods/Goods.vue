<template>
  <div class="t">
    <div class="top">
      <span class="left">{{ time }}</span>
      <!-- <div class="right"> -->
        <span class="font1">{{ jingji }}</span>
            <span class="font2">￥<i>{{ jingjiCost }}</i></span>
        <span class="font1">{{ shangwu }}</span>
            <span class="font2">￥<i>{{ shangwuCost }}</i>
          </span>
      <!-- </div> -->
      <ul>
      <li>出发地:福州</li>
      <li>目的地:泉州</li>
    </ul>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    time: {
      type: String,
      default: "",
    },
    jingji: {
      type: String,
      default: "经济型:",
    },
    jingjiCost: {
      type: Number,
      default: 0,
    },
    shangwu: {
      type: String,
      default: "商务型:",
    },
    shangwuCost: {
      type: Number,
      default: 0,
    },
  },
};
</script>

<style lang="less" scoped>
.t{
    margin-top: 100px;
}
.top {
  padding: 0, 15px;
  border-bottom: 1px red;
  margin-top: 14px;
  float: left;
  width:390px;
}
div {
  left: 14px;
  top: 268px;
  width: 362px;
  height: 118px;
  line-height: 20px;
  border-radius: 4px;
  background-color: rgba(255, 255, 255, 100);
  color: rgba(16, 16, 16, 100);
  font-size: 14px;
  //   text-align: center;
  font-family: -apple-system;
}
.left{
    margin-left: 10px;
}
.font1 {
margin-left: 80px;
  left: 173px;
  top: 281px;
  width: 87px;
  height: 16px;
  color: rgba(153, 153, 153, 100);
  font-size: 14px;
  text-align: left;
  font-family: PingFangSC-regular;
}
.font2{
    margin-right: -50px;
    color:#F9872A;
}
</style>