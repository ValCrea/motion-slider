<script setup lang="ts">
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";
import "swiper/css/scrollbar";
import { Swiper, SwiperSlide } from "swiper/vue";
import { Navigation, Pagination, Scrollbar, A11y } from "swiper";

const onSwiper = (swiper: any) => {
  console.log(swiper);
};
const onSlideChange = () => {
  console.log("slide change");
};

const modules = [Navigation, Pagination, Scrollbar, A11y];
</script>

<template>
  <Swiper
    :modules="modules"
    :slides-per-view="2"
    :space-between="50"
    navigation
    :pagination="{ clickable: true }"
    :scrollbar="{ draggable: true }"
    @swiper="onSwiper"
    @slideChange="onSlideChange"
  >
    >

    <template v-for="index in 10" :key="index">
      <SwiperSlide v-slot="{ isActive, isNext }">
        <div
          :class="{ 'slider-blue': isActive, 'slider-green': isNext }"
          class="slider-element"
        >
          Slide {{ index }}
        </div>
      </SwiperSlide>
    </template>
  </Swiper>
</template>

<style scoped>
.slider-element {
  width: 600px;
  max-width: 90%;
  height: 500px;
  margin-inline: auto;

  font-size: 30px;
  background-color: lightcoral;

  display: flex;
  align-items: center;
  justify-content: center;
}

.slider-blue {
  background-color: lightblue;
}
.slider-green {
  background-color: lightgreen;
}
</style>
