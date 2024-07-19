<template>
  <div class="major">
    <div class="wrapper">
      <div class="major__inner">
        <div class="major__title title">2022 - рекордный по количеству форс-мажоров</div>
        <div class="major__subtitle">В этих условиях бизнесу важно отвечать на вопросы:</div>
        <div class="major__list">
          <div class="major__item" v-for="(item, i) in card" :key="i">
            <div class="major__item-img">
              <img :src="item.img" alt="svg">
            </div>
            <div class="major__item-text">{{ item.text }}</div>
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
      card: []
    }
  },
  async mounted() {
    const cards = []
    cards.push(
      {
        img: (await import("@/assets/img/major/item1.svg")).default,
        text : 'Как организовать процесс без паники и убаюкивающего оптимизма?',
      },
      {
        img: (await import("@/assets/img/major/item2.svg")).default,
        text : 'Как определить приоритеты, когда условия постоянно меняется?',
      },
      {
        img: (await import("@/assets/img/major/item3.svg")).default,
        text : 'Какие выбрать стратегии с учетом возможных сценариев?',
      },
    )
    this.card = cards
	},
}
</script>

<style lang="scss">
.major {
  &__title {
    @media(max-width: 767px) {
      margin-bottom: 15px;
    }
  }
  &__subtitle {
    text-align: center;
    color: var(--grey2);
    margin-bottom: 40px;
    font-size: 24px;
    font-weight: 600;
    @media(max-width: 767px) {
      font-size: 16px;
      margin-bottom: 30px;
    }
  }
  &__list {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 30px;
    @media(max-width: 767px) {
      grid-template-columns: 1fr;
    }
  }
  &__item {
    text-align: center;
  }
  &__item-img {
    display: block;
    width: 55px;
    height: 55px;
    background-color: var(--lightGreen);
    border-radius: 50%;
    position: relative;
    margin: 0 auto 15px;
    @media(max-width: 767px) {
      width: 50px;
      height: 50px;
    }
    img {
      position: absolute;
      left: 50%;
      top: 50%;
      transform: translate(-50%, -50%);
    }
  }
  &__item-text {
    font-size: 20px;
    font-weight: 500;
    line-height: 120%;
    color: var(--grey);
    @media(max-width: 767px) {
      font-size: 18px;
    }
  }
}
</style>