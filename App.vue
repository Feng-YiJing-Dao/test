<template>
  <div>
    <!-- 头部区域 -->
    <Header></Header>
    <!-- 中间主要区域 -->
    <Main></Main>
    <!-- 底部区域 -->
    <Footer></Footer>
  </div>
</template>

<script>
import Header from "@/components/Header/Header.vue";
import Main from "@/components/Main/Main.vue";
import Footer from "@/components/Footer/Footer.vue";

export default {
  name: "App",
  components: {
    Header,
    Footer,
    Main
  },
  data() {
    return {
      activeName: "second",
      datelist: [1, 2, 3, 4, 5],
    };
  },
  methods: {
    handleClick(tab, event) {
      console.log(tab, event);
    },
  },
  watch: {},
  computed: {},
  filters: {},
};
</script>

<style lang="less">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  // margin-top: 60px;
  // background-color: #f2f3f694;
}
body{
  margin:0px;
  padding:0px;
  background-color: #F8F8F8;
}
.div{
  // position: relative;
}
.Footer {
  position: absolute;
  left: 0px;
  top: 764px;
  width: 390px;
  height: 80px;
  line-height: 20px;
  text-align: center;
}
</style>
