<template>
  <swiper
    :slides-per-view="slidesPerView"
    :space-between="10"
    :navigation="true"
    :modules="modules"
    :loop="false"
    @swiper="onSwiper"
    @slideChange="onSlideChange"
    @reachEnd="onReachEnd"
  >
    <swiper-slide v-for="item in data">
      <CustomSlide v-bind="item">
        <template #tr>
          <div class="p-2">
            <strong class="bg-blue-500 border-blue-500 border text-white lowercase px-3 py-1.5 rounded text-[12px] font-medium">
              {{item.date}}
            </strong>
          </div>
        </template>
        <template #bl>
          <div class="p-2">
            <span class="text-white font-medium">{{item.text}}</span>
          </div>
        </template>

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
import { faker } from "@faker-js/faker"

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  props: ['slidesPerView'],
  setup() {
    const onSwiper = (swiper) => {
      console.log(swiper);
    };
    const onSlideChange = () => {
      console.log('slide change');
    };

    const onReachEnd = () => {
      const more = Array.from(Array(8)).map(x => (
      {
        date: new Intl.DateTimeFormat('en-US').format(faker.date.soon(10, '2020-01-01T00:00:00.000Z')),
        image: faker.image.nature(1280, 720, true),
        text: faker.lorem.words(4)
      }))

      data.value.push(...more)
    };

    const data = ref(Array.from(Array(8)).map(x => (
      {
        date: new Intl.DateTimeFormat('en-US').format(faker.date.soon(10, '2020-01-01T00:00:00.000Z')),
        image: faker.image.nature(1280, 720, true),
        text: faker.lorem.words(4)
      })))

    return {
      data,
      modules: [Autoplay, Pagination, Navigation],
      onSwiper,
      onSlideChange,
      onReachEnd
    };
  },
};
</script>