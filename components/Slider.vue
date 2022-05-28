<template>
  <swiper
    :slides-per-view="2"
    :space-between="10"
    :pagination="{
      clickable: true,
    }"
    :navigation="true"
    :modules="modules"
    :loop="false"
    @swiper="onSwiper"
    @slideChange="onSlideChange"
  >
    <swiper-slide v-for="x in data">
      <CustomSlide v-bind="x">
      </CustomSlide>
    </swiper-slide>
  </swiper>
</template>
<script>
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue';

// Import Swiper styles
import 'swiper/css';
import "swiper/css/pagination";
import "swiper/css/navigation";
import { Autoplay, Pagination, Navigation } from "swiper";

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const onSwiper = (swiper) => {
      console.log(swiper);
    };
    const onSlideChange = () => {
      console.log('slide change');
    };

    const data = [
      {
        left: 'red',
        right: 'blue'
      },
      {
        left: 'green',
        right: 'yellow'
      },
      {
        left: 'red',
        right: 'blue'
      },
      {
        left: 'pink',
        right: 'yellow'
      },
      {
        left: 'red',
        right: 'blue'
      }
    ]

    return {
      data,
      modules: [Autoplay, Pagination, Navigation],
      onSwiper,
      onSlideChange,
    };
  },
};
</script>