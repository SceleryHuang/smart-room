<template>
  <div class="logo">
    <div class="logo_word">天气</div>
    <img class="logo-img" src="../../public/pic/heavy_snow.png" />
    <div>{{ weather_detail }}</div>
    <ul class="weather-ul">
      <li v-for="item of weather_suggList" :key="item.id" class="weather-li">
        <div>
          <img :src="item.imgUrl" />{{ item.label }}
          <div class="weather-degree">{{ item.degree }}</div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      weather_detail: "小雨15度",
      weather_suggList: [
        {
          id: 1,
          imgUrl: require("../../public/pic/dressing.png"),
          label: "穿衣指数",
          degree: "较舒适"
        },
        {
          id: 2,
          imgUrl: require("../../public/pic/flu.png"),
          label: "感冒指数",
          degree: "易发"
        },
        {
          id: 3,
          imgUrl: require("../../public/pic/uv.png"),
          label: "紫外线指数",
          degree: "最弱"
        }
      ]
    };
  }
};
</script>

<style>
.logo {
  text-align: center;
}
.logo_word {
  font-size: 25px;
}
.logo-img {
  text-align: center;
  position: relative;
}
.weather-li {
  list-style: none;
  text-align: center;
  font-size: 15px;
  height: 65px;
  margin-left: -50px;
  margin-bottom: 10px;
  margin-top: 20px;
}
.weather-degree {
  padding-left: 40px;
  text-align: center;
}
</style>
