<template>
  <div class="page">
    <header class="page__header">
      <span class="page__header__region">Seoul, Korea</span>
      <span class="page__header__data">1900. 01. 01</span>
    </header>
    <body class="page__body">
      <div class="page__body__main">
        <div class="data-box">
          <WEATHERBOX />
          <div class="data-box__graph-box">
          <GRAPH />
          <GRAPH />
          <GRAPH />
        </div>
      </div>
      <MAP />      
    </div>
    <div class="page__body__daily">
        <DAILYWEATHER />
      </div>
    </body> 
  </div>
</template>

<script>
import WEATHERBOX from "../molecules/WeatherBox.vue";
import MAP from "../molecules/Map.vue"
import DAILYWEATHER from "./molecules/DailyWeather.vue";
import GRAPH from "../molecules/Graph.vue"

export default {
  components: { WEATHERBOX, MAP, DAILYWEATHER, GRAPH },
  data () {
    return {};
  },
};
</script>

<style lang="scss" scoped>
.page {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  width: 100%;
  height: 100%;

  &__header {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;

    &__region{
      font-size: 48px;
    }
    &__date{
      font-weight: 300;
    }
  }
  &__body {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;

    width: 100%;

    &__main {
      display: flex;
      align-items: center;
      justify-content: center;

      gap: 100px;
    }
    &__daily{
      display: flex;
      align-items: center;
      justify-content: flex-start;

      width: 82.5%;

      margin-top: 48px;
      gap: 48px;

      overflow-x: scroll;

    }
  }
}
</style>
