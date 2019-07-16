<template>
  <div class="logo">
    <div class="logo_word">天气</div>
    <img class="logo-img" src="./pic/heavy_snow.png" />
    <div>{{ item.weather_detail }}</div>
    <ul>
      <router-link
        tag="li"
        class="item border-bottom"
        v-for="item of list"
        :key="item.id"
        :to="'/weather/' + item.id"
      >
        <div>
          <img :src="item.imgUrl" />{{ item.label }}
          <div>{{ item.degree }}</div>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      weather: "小雨15度"
    };
  },
  props: {
    list: Array
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
