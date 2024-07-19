<template>
  <Swiper
    class="slider"
    :modules="modules"
    :loop="options.loop"
    :navigation="options.navigation"
    :slidesPerView="options.slidesPerView"
    :slidesPerGroup="options.slidesPerGroup"
    :centeredSlides="options.centeredSlides"
    :spaceBetween="options.spaceBetween"
    :pagination="options.pagination"
    :breakpoints="options.breakpoints"
    :effect="options.effect"
    :mousewheel="options.mousewheel"
  >
    <SwiperSlide
      v-for="(slide, i) in slider"
      :key="i"
    >
      <div v-if="slide.feedBack" class="slider__wrap">
        <div class="slider__top">
          <div class="slider__photo">
            <img :src="slide.photo" alt="">
          </div>
          <div class="slider__info">
            <div class="slider__name">{{ slide.name }}</div>
            <div class="slider__place">{{ slide.place }}</div>
          </div>
        </div>
        <div class="slider__body">
          <div class="slider__description">{{ slide.description }}</div>
        </div>
      </div>

      <div v-else class="slider__wrap">
        <div class="slider__img">
          <img :src="slide.img" alt="...">
          <div class="slider__text">{{ slide.text }}</div>
        </div>
      </div>
    </SwiperSlide>
    <SwiperControls />
  </Swiper>
</template>

<script>
import { Swiper, SwiperSlide } from 'swiper/vue';

import 'swiper/css';

import 'swiper/css/effect-coverflow';
import 'swiper/css/effect-fade';
import 'swiper/css/pagination';
import 'swiper/css/navigation';

import { Pagination, Navigation, Mousewheel, EffectCoverflow, EffectFade } from 'swiper/modules';
export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  props: {
    slider: {type: Array, default: [], require: false},
    options: {type: Object, default: {}, require: false}
  },
  mounted() {
    console.log(this.options)
  },
  setup() {
      return {
        modules: [ Pagination, Navigation, Mousewheel, EffectCoverflow, EffectFade]
      };
    },
}

</script>

<style lang="scss"></style>