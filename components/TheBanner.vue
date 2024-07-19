<template>
  <div class="banner">
    <div class="wrapper">
      <TheBreadCrumbs :breadCrumbs="breadCrumbs" class="banner__bredcrumbs" />
      <div class="banner__inner">
        <div class="banner__date">
          <p>8-9 декабря 2022</p>
          <UITheButton :label="'Семинар-практикум'" class="btn btn-small btn-small__light"></UITheButton>
        </div>
        <h1 class="banner__title">Жизнь и смерть вашего бизнеса: <span>стабилизация в условиях санкций</span></h1>
        <div class="banner__subtitle">Куда вести компанию, когда горизонт планирования сужается?</div>
        <div class="banner__btn">
          <UITheButton :label="'Узнать подробнее'"  class="btn btn-big btn-big__dark" />
        </div>
        <div class="banner-description">
          <div class="banner-description__title">Демид Голиков</div>
          <div class="banner-description__subtitle">Директор ГК «Институт Тренинга - АРБ Про», эксперт&nbsp;ЦБО</div>
          <div class="banner-description__company">
            <img src="@/assets/img/company.svg" class="block__desktop" alt="company">
            <img src="@/assets/img/company2.svg" class="block__mobile" alt="company">
            <img src="@/assets/img/CBE.svg" alt="company">
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      breadCrumbs: [
        {
          name: 'Все программы',
          url: '#',
          current: false
        },
        {
          name: 'Управление финансами в условиях кризиса',
          url: '#',
          current: true
        }
      ],
    }
  }
}
</script>

<style lang="scss">
.banner {
  background-image: url('@/assets/img/bg.webp');
  background-position: 50% 50%;
  background-color: #F0F1F3;
  background-repeat: no-repeat;
  background-size: cover;
  // padding-bottom: 9%;
  position: relative;
  z-index: 2;
  overflow: hidden;
  &::after {
    content: '';
    display: block;
    width: 630px;
    height: 745px;
    background-image: url('@/assets/img/man.webp');
    background-position: 50% 50%;
    background-repeat: no-repeat;
    background-size: cover;
    position: absolute;
    right: 0;
    bottom: 0px;
    z-index: -1;
    @media(max-width: 991px) {
      width: 430px;
      height: 545px;
      bottom: -20px;
      background-size: contain;
    }
    @media(max-width: 767px) {
      width: 345px;
      height: 400px;
      right: -25px;
    }
  }
  &__inner {
    position: relative;
  }
  &__date {
    display: flex;
    align-items: flex-end;
    margin-bottom: 15px;
    padding-top: 130px;
    @media(max-width: 1023px) {
      padding-top: 50px;
      flex-direction: column;
      align-items: flex-start;
    }
    @media(max-width: 767px) {
      align-items: center;
      margin-bottom: 20px;
    }
    p {
      color: var(--lightGreen);
      font-size: 20px;
      font-weight: 600;
      padding-right: 20px;
      @media(max-width: 1023px) {
        padding-right: 0;
        order: 2;
      }
    }
    button {
      @media(max-width: 1023px) {
        order: 1;
        margin-bottom: 10px;
      }
    }
  }
  &__title {
    font-size: 52px;
    font-weight: 500;
    line-height: 120%;
    max-width: 50%;
    margin-bottom: 25px;
    @media(max-width: 991px) {
      max-width: 100%;
      font-size: 40px
    }
    @media(max-width: 767px) {
      font-size: 32px;
      text-align: center;
    }
    span {
      color: var(--lightGreen);
      font-weight: 600;
    }
  }
  &__subtitle {
    font-size: 24px;
    font-weight: 300;
    margin-bottom: 40px;
    max-width: 40%;
    @media(max-width: 991px) {
      max-width: 100%;
    }
    @media(max-width: 767px) {
      text-align: center;
      font-size: 20px;
    }
  }
  &__btn {
    padding-bottom: 130px;
    @media(max-width: 991px) {
      padding-bottom: 500px;
    }
    @media(max-width: 767px) {
      margin: 0 auto 15px;
      text-align: center;
      padding-bottom: 400px;
    }
    button {}
  }
  &__bredcrumbs {
    @media(max-width: 1023px) {
      display: none;
    }
  }
}
.banner-description {
  background-color: var(--white);
  border-radius: 10px;
  padding: 40px 15px 15px;
  display: inline-block;
  max-width: 375px;
  position: absolute;
  right: 60px;
  bottom: 30px;
  @media(max-width: 991px) {
    right: auto;
    left: 55px;
  }
  @media(max-width: 767px) {
    padding: 15px;
    max-width: 250px;
    bottom: 10px;
  }
  &__title {
    color: var(--green3);
    font-size: 29px;
    font-weight: 600;
    margin-bottom: 10px;
    @media(max-width: 767px) {
      font-size: 18px;
    }
  }
  &__subtitle {
    color: var(--grey);
    font-size: 15px;
    line-height: 160%;
    font-weight: 500;
    margin-bottom: 10px;
    @media(max-width: 767px) {
      font-size: 12px;
    }
  }
  &__company {
    display: flex;
    justify-content: space-between;
    img {
      @media(max-width: 767px) {
        height: 20px;
      }
    }
  }
}
</style>