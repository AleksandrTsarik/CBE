<template>
  <div class="slider-block">
    <div class="wrapper">
      <div class="slider-block__title title">Как все будет проходить?</div>
      <div class="slider-block__subtitle">Предметный разговор без купюр:</div>
    </div>
    <UITheSwiper
      :slider="slider"
      :options="optionsSlider" 
      class="slider-small"
    />
    <div class="wrapper"><UITheButton :label="'Узнать стоимость'" class="btn btn-big btn-big__dark" /></div>
    
  </div>

</template>

<script>
export default {
  data() {
    return {
      slider: [],
      optionsSlider: {
        loop: true,
        slidesPerView: 1.5,
        slidesPerGroup: 1,
        centeredSlides: true,
        spaceBetween: 35,
        pagination: false,
        navigation: true,
        modules: "modules",
        mousewheel: true,
        breakpoints: {
          575: {
            slidesPerView: 2,
          }
        },
        navigation: true
      }
    }
  },
  async mounted() {
    const sliders = []
    sliders.push(
      {
        img: (await import("@/assets/img/slider/item1.webp")).default,
        text: 'Можно и нужно задавать все волнующие вопросы и получать ответы по существу',
      },
      {
        img: (await import("@/assets/img/slider/item2.webp")).default,
        text: 'Можно и нужно задавать все волнующие вопросы и получать ответы по существу',
      },
      {
        img: (await import("@/assets/img/slider/item3.webp")).default,
        text: 'Можно и нужно задавать все волнующие вопросы и получать ответы по существу',
      },
      {
        img: (await import("@/assets/img/slider/item1.webp")).default,
        text: 'Можно и нужно задавать все волнующие вопросы и получать ответы по существу',
      },
    )
    this.slider = sliders
	},
}
</script>

<style lang="scss">
.slider-block {
  &__title {}
  &__subtitle {
    text-align: center;
    margin-bottom: 40px;
    font-size: 24px;
    font-weight: 600;
    color: var(--grey2);
  }
  .btn {
    margin: 0 auto;
    display: block;
  }
}
.slider {
  &__wrap {
    height: 100%;
  }
  &__img {
    position: relative;
    border-radius: 15px;
    overflow: hidden;
    height: 100%;
    img{
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }
  &__text {
    position: absolute;
    bottom: 30px;
    padding: 0 50px;
    width: 100%;
    left: 50%;
    transform: translateX(-50%);
    z-index: 1;
    color: var(--white);
    text-align: center;
    font-size: 20px;
    font-weight: 500;
    @media(max-width: 1023px) {
      font-size: 18px;
      padding: 0 25px;
    }
    @media(max-width: 767px) {
      font-size: 16px;
      padding: 0 15px;
    }
  }
}
.slider-small {
  height: 400px;
  margin-bottom: 50px;
  @media(max-width: 1023px) {
    height: 285px;
  }
  @media(max-width: 767px) {
    height: 295px;
  }
  .swiper-button-prev, .swiper-button-next {
    &::after {
      color: var(--white);
    }
  }
  .swiper-button-prev {
    left: 15%;
    @media(max-width: 1023px) {
      left: 10%;
    }
    @media(max-width: 575px) {
      display: none;
    }
  }
  .swiper-button-next {
    right: 15%;
    @media(max-width: 1023px) {
      right: 10%;
    }
    @media(max-width: 575px) {
      display: none;
    }
  }
}
</style>