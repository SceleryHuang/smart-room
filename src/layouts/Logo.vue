<template>
  <div class="logo">
    <div class="logo_date">{{ date | formaDate }}</div>
    <div class="logo_word">智能家居系统</div>
    <div class="logo_word">智能家居系统</div>
    <div class="logo_word">智能家居系统</div>
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
    formaDate: function() {
      var date = new Date();
      var year = date.getFullYear();
      var month = padaDate(date.getMonth() + 1);
      var day = padaDate(date.getDate());
      var hours = padaDate(date.getHours());
      var minutes = padaDate(date.getMinutes());
      var seconds = padaDate(date.getSeconds());
      return (
        year +
        "年" +
        month +
        "月" +
        day +
        "日" +
        hours +
        "时" +
        minutes +
        "分" +
        seconds +
        "秒"
      );
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
</style>
