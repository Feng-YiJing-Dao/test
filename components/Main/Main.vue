<template>
<div>
  <div class="main">
      <div class="tabs" v-for="(item,index) in datelist">
        <button :class={current:isCurrent[index]}>{{item.d}}</br>{{item.date}}</button>
      </div>
    <el-date-picker class="datepicker" v-model="value1" type="date" placeholder="" @change="timeChange">
    </el-date-picker>
  </div>
      <Goods
      v-for="item in list"
      :time="item.time"
      :jingjiCost="item.jingjiCost"
      :shangwuCost="item.shangwuCost"
    ></Goods>
</div>
</template>

<script>
import Goods from "@/components/Goods/Goods.vue";

export default {
  components: {
    Goods,
  },
  props: {
    clickName: {
      type: String,
      default: "全部日期",
    },
  },
  data() {
    return {
      datelist: [
        { d: "周三", date: "07-21" },
        { d: "周四", date: "07-22" },
        { d: "周五", date: "07-23" },
        { d: "周六", date: "07-24" },
        { d: "周日", date: "07-25" },
      ],
      list: [
        {
          time: "10:00",
          jingjiCost: 35,
          shangwuCost: 45,
        },
        {
          time: "10:00",
          jingjiCost: 35,
          shangwuCost: 45,
        },
      ],
      isCurrent: [false, false, false, false, true],
      value: new Date(),
      pickerOptions: {
        disabledDate(time) {
          return time.getTime() > Date.now();
        },
        shortcuts: [
          {
            text: "今天",
            onClick(picker) {
              picker.$emit("pick", new Date());
            },
          },
          {
            text: "昨天",
            onClick(picker) {
              const date = new Date();
              date.setTime(date.getTime() - 3600 * 1000 * 24);
              picker.$emit("pick", date);
            },
          },
          {
            text: "一周前",
            onClick(picker) {
              const date = new Date();
              date.setTime(date.getTime() - 3600 * 1000 * 24 * 7);
              picker.$emit("pick", date);
            },
          },
        ],
      },
      value1: "",
      value2: "",
    };
  },
  methods: {
    timeChange: function (val) {
      //   console.log(val);
      let current = 0;
      let month = val.getMonth();
      let date = val.getDate();
      if (parseInt(month) < 10) month = "0" + month;
    //   if (parseInt(date) < 10) date = "0" + date;
      for (let i = 0; i < this.datelist.length; i++) {
        if (this.datelist[i].date === month + "-" + date) {
          this.isCurrent[i] = true;
          current = i;
        }
      }
      let cnt = 0;
      for (let i = 0; i < this.datelist.length; i++) {
        this.datelist[i].date = month + "-" + (date+cnt);
        cnt++;
        this.isCurrent[i] = false;
      }
      this.isCurrent[current] = true;
    //   改变面板数据
        this.list=[        {
          time: "10:00",
          jingjiCost: 325,
          shangwuCost: 445,
        },
        {
          time: "10:00",
          jingjiCost: 351,
          shangwuCost: 415,
        },];
    }
  },
};
</script>

<style lang="less" scoped>
.main {
  position: relative;
  background-color: white;
  left: 0px;
  top: 100px;
  padding-top: 10px;
  padding-bottom: 10px;
  width: 390px;
  height: 60px;
  line-height: 60px;
  text-align: center;
  vertical-align: center;
}
button {
  //   display: inline-block;
  float: left;
  margin-left: 10px;
  left: 13px;
  top: 202px;
  width: 55px;
  height: 44px;
  border-radius: 10px;
  border: 0;
  color: rgba(85, 85, 85, 100);
  font-size: 12px;
  text-align: center;
  font-family: PingFangSC-regular;
  overflow: hidden;
}
.datepicker {
  position: absolute;
  left: 342px;
  //   top: 188px;
  width: 48px;
  height: 60px;
  line-height: 20px;
  text-align: center;
  box-shadow: 0px 0px 2px 0px rgba(0, 0, 0, 0.23);
  overflow: hidden;
}

.current {
  background-color: #3894ff;
  color: aliceblue;
}
.Goods {
  position: absolute;
  padding: 10px, 15px;
  margin-top: 10px;
}
</style>