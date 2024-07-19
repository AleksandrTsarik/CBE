<template>
  <div class="wrapper">
    <div class="slider-feedback-block">
      <div class="slider-feedback-block__title title">Что говорят о практикуме?</div>
    </div>
    <UITheSwiper
      :slider="slider"
      :options="optionsSlider" 
      class="slider-big"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      slider: [],
      optionsSlider: {
        loop: false,
        slidesPerView: 2,
        slidesPerGroup: 1,
        centeredSlides: false,
        spaceBetween: 35,
        pagination: {
          type: 'fraction'
        },
        navigation: true,
        modules: "modules",
        mousewheel: false,
        breakpoints: {
          1023: {
            slidesPerView: 3.5,
          },
          575: {
            slidesPerView: 3,
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
        photo: (await import("@/assets/img/slider-feedback/item1.png")).default,
        name: 'Иван Иванов',
        place: 'Директор по развитию',
        description: 'Задача организации, в особенности же постоянное информационно-пропагандистское обеспечение нашей деятельности требуют определения и уточнения дальнейших направлений развития. С другой стороны сложившаяся структура организации позволяет выполнять важные задания по разработке новых предложений.',
        feedBack: true
      },
      {
        photo: (await import("@/assets/img/slider-feedback/item2.png")).default,
        name: 'Иван Иванов',
        place: 'Директор по развитию',
        description: 'Задача организации, в особенности же постоянное информационно-пропагандистское обеспечение нашей деятельности требуют определения и уточнения дальнейших направлений развития. С другой стороны сложившаяся структура организации позволяет выполнять важные задания по разработке новых предложений.',
        feedBack: true
      },
      {
        photo: (await import("@/assets/img/slider-feedback/item3.png")).default,
        name: 'Иван Иванов',
        place: 'Директор по развитию',
        description: 'Задача организации, в особенности же постоянное информационно-пропагандистское обеспечение нашей деятельности требуют определения и уточнения дальнейших направлений развития. С другой стороны сложившаяся структура организации позволяет выполнять важные задания по разработке новых предложений.',
        feedBack: true
      },
      {
        photo: (await import("@/assets/img/slider-feedback/item4.png")).default,
        name: 'Иван Иванов',
        place: 'Директор по развитию',
        description: 'Задача организации, в особенности же постоянное информационно-пропагандистское обеспечение нашей деятельности требуют определения и уточнения дальнейших направлений развития. С другой стороны сложившаяся структура организации позволяет выполнять важные задания по разработке новых предложений.',
        feedBack: true
      },
      {
        photo: (await import("@/assets/img/slider-feedback/item1.png")).default,
        name: 'Иван Иванов',
        place: 'Директор по развитию',
        description: 'Задача организации, в особенности же постоянное информационно-пропагандистское обеспечение нашей деятельности требуют определения и уточнения дальнейших направлений развития. С другой стороны сложившаяся структура организации позволяет выполнять важные задания по разработке новых предложений.',
        feedBack: true
      },
      {
        photo: (await import("@/assets/img/slider-feedback/item2.png")).default,
        name: 'Иван Иванов',
        place: 'Директор по развитию',
        description: 'Задача организации, в особенности же постоянное информационно-пропагандистское обеспечение нашей деятельности требуют определения и уточнения дальнейших направлений развития. С другой стороны сложившаяся структура организации позволяет выполнять важные задания по разработке новых предложений.',
        feedBack: true
      },
      {
        photo: (await import("@/assets/img/slider-feedback/item3.png")).default,
        name: 'Иван Иванов',
        place: 'Директор по развитию',
        description: 'Задача организации, в особенности же постоянное информационно-пропагандистское обеспечение нашей деятельности требуют определения и уточнения дальнейших направлений развития. С другой стороны сложившаяся структура организации позволяет выполнять важные задания по разработке новых предложений.',
        feedBack: true
      },

    )
    this.slider = sliders
	},
}
</script>

<style lang="scss">
.slider {
  &__wrap {
    padding: 30px;
    background-color:#F2F3F5;
    border-radius: 8px;
    @media(max-width: 1023px) {
      padding: 10px;
    }
  }
  &__top {
    display: grid;
    grid-template-columns: 45px 1fr;
    gap: 30px;
    margin-bottom: 20px;
    @media(max-width: 1023px) {
      margin-bottom: 10px;
    }
  }
  &__photo {
    width: 45px;
    height: 45px;
    border-radius: 50%;
    overflow: hidden;
    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }
  &__info {}
  &__name {
    color: #000;
    font-size: 18px;
    font-weight: 600;
    margin-bottom: 5px;
    @media(max-width: 1023px) {
      font-size: 16xp;
    }
    @media(max-width: 767px) {
      font-size: 14px;
    }
  }
  &__place {
    font-size: 16px;
    color: var(--grey3);
    @media(max-width: 1023px) {
      font-size: 12px;
    }
    @media(max-width: 767px) {
      font-size: 8px;
    }
  }
  &__body {}
  &__description {
    color: var(--grey);
    font-size: 16px;
    letter-spacing: -2%;
    line-height: 120%;
    @media(max-width: 1023px) {
      font-size: 10px;
    }
    @media(max-width: 767px) {
      font-size: 8px;
    }
  }
}
.slider-big {
  &.swiper {
    overflow: visible;
  }
  .swiper-wrapper {
    padding-bottom: 70px;
  }
  .swiper-pagination {
    display: inline-block;
    font-size: 20px;
    color: var(--grey3);
    margin: 0 10px 5px;
    z-index: 1;
  }
  .swiper-pagination-current {
    color: var(--lightGreen);
  }
  .swiper-button-prev, .swiper-button-next {
    width: 55px;
    height: 55px;
    border-radius: 50%;
    border: solid 1px #E4E7EC;
    background-color: var(--white);
    top: auto;
    bottom: 0px;
    z-index: 10;
    &:after {
      content: '';
      background-image: url('@/assets/img/arrow-dark.svg');
      background-position: 50% 50%;
      background-repeat: no-repeat;
      width: 25px;
      height: 25px;
      display: block;
      position: absolute;
      left: 50%;
      top: 50%;
      transform: translate(-50%, -50%)
    }

  }
  .swiper-button-next {
      background-color: var(--lightGreen);
      right: 41.5%;
      @media(max-width: 1200px) {
        right: 36%;
      }
      @media(max-width: 767px) {
        right: 16%;
      }
      &:after {
        background-image: url('@/assets/img/arrow-light.svg');
        transform: translate(-50%, -50%) rotate(180deg)
      }
    }
  .swiper-button-prev {
    left: 43%;
    @media(max-width: 1200px) {
      left: 38%;
    }
    @media(max-width: 767px) {
      left: 22%;
    }
  }
}
.slider-feedback {
  overflow-x: hidden;
}
</style>