<template>
  <div class="logo">
    <div class="logo_date">{{ date | formaDate1 }}</div>
    <div class="logo_date">{{ date | formaDate2 }}</div>
    <div class="logo_word">智能家居系统</div>
    <img class="logo-img" src="./pic/house.png" />
    <button class="logo-btn">模式设置</button>
    <button class="logo-btn">手动</button>
  </div>
</template>

<script>
var padaDate = function(value) {
  return value < 10 ? "0" + value : value;
};
export default {
  data() {
    return {
      date: new Date()
    };
  },
  filters: {
    formaDate1: function() {
      var date = new Date();
      var year = date.getFullYear();
      var month = padaDate(date.getMonth() + 1);
      var day = padaDate(date.getDate());
      return year + "年" + month + "月" + day + "日";
    },
    formaDate2: function() {
      var date = new Date();
      var hours = padaDate(date.getHours());
      var minutes = padaDate(date.getMinutes());
      var seconds = padaDate(date.getSeconds());
      return hours + "时" + minutes + "分" + seconds + "秒";
    }
  },
  mounted() {
    let _this = this;
    this.timer = setInterval(() => {
      _this.date = new Date();
    }, 1000);
  },
  beforeDestroy() {
    if (this.timer) {
      clearInterval(this.timer);
    }
  }
};
</script>

<style>
.logo {
  /*height: 64px;*/
  /*line-height: 64px;*/
  text-align: center;
}
.logo_date {
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 2;
  font-size: 25px;
}
.logo_word {
  font-size: 25px;
}
.logo-img {
  text-align: center;
  position: relative;
}

.logo-btn {
  height: 30px;
  width: 75px;
  position: relative;
  display: block;
  margin-left: 85px;
  margin-top: 15px;
}
</style>
