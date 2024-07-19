<template>
  <div class="wrapper">
    <div class="workshop-block__inner">
      <div class="workshop-block__title title">Этот практикум необходим:</div>
      <div class="workshop-block__list">
        <div class="workshop-block__item" v-for="(item, i) in list" :key="i">
          <div class="workshop-block__item-title">{{ item.title }}</div>
          <div class="workshop-block__item-text">{{ item.text }}</div>
        </div>
      </div>
      <div class="workshop-block__row">
        <TheSvg :type="'atention'" />Чтобы получить результат, лучше пройти практикум командой руководителей
      </div>
      <div class="workshop-block__btn">
        <UITheButton :label="'Узнать специальную цену для команды'" class="btn btn-big btn-big__dark" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      list: [
        {
          title: 'Собственникам бизнеса',
          text: 'Чтобы понять, как действовать дальше, “заразиться” идеями и получить детальный фидбэк на свою стратегию'
        },
        {
          title: 'Финансовым директорам',
          text: 'Чтобы узнать, на чем можно сэкономить, а где - найти новые возможности заработать бизнесу'
        },
        {
          title: 'Коммерческим директорам',
          text: 'Чтобы расширить долю рынка и увеличить  прибыль и рентабельность, пока конкуренты в растерянности'
        },
        
      ]
    }
  }
}
</script>

<style lang="scss">
.workshop {
  background: linear-gradient(134.40deg, rgb(0, 66, 65),rgb(4, 92, 94),rgb(4, 92, 94),rgb(4, 92, 94));
  border-radius: 30px;
  position: relative;
  overflow: hidden;
  &::after {
    content: '';
    display: block;
    width: 500px;
    height: 465px;
    background-image: url('@/assets/img/line.svg');
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    transform: rotate(0);
    opacity: 0.5;
    position: absolute;
    right: -275px;
    bottom: -45px;
    @media(max-width: 767px) {
      display: none;
      left: 0;
      background: linear-gradient(130.80deg, rgb(0, 89, 88) 5.649%,rgb(12, 153, 156) 89.764%);
      border-radius: 15px;
    }
  }
}
.workshop-block {
  text-align: center;
  color: var(--white);
  &__inner {
    padding: 75px 0;
  }
  &__title {
    color: var(--white);
  }
  &__row {
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 50px;
    svg {
      margin-right: 15px;
    }
  }
  &__btn {
    margin: 0 auto;
    display: block;
    text-align: center;
  }
  &__list {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 50px;
    margin-bottom: 50px;
    margin-top: 40px;
    @media(max-width: 767px) {
      grid-template-columns: 1fr;
    }
  }
  &__item {
    position: relative;
    counter-increment: num;
    z-index: 10;
    padding-top: 20px;
    @media(max-width: 767px) {
      padding-left: 20px;
    }
    &::before {
      content: "0" counter(num);
      font-size: 115px;
      letter-spacing: -2px;
      font-weight: 500;
      line-height: 100%;
      text-align: center;
      color: var(--lightGreen);
      display: block;
      position: absolute;
      top: -20px;
      left: -30px;
      z-index: -1;
      @media(max-width: 767px) {
        left: 0;
        top: -10px;
        font-size: 80px;
      }
    }
  }
  &__item-title {
    font-size: 24px;
    font-weight: 600;
    margin-bottom: 15px;
    text-align: left;
  }
  &__item-text {
    font-size: 16px;
    font-weight: 400;
    line-height: 140%;
    text-align: left;
  }
}
</style>