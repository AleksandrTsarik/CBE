<template>
  <div class="work">
    <div class="work__wrap">
      <div class="work__title title">Что будем делать на практикуме? </div>
      <div class="work__subtitle">В основе программы — стратегический инструментарий АРБ Про: PIL-подход, карта рынка, матрица обновления&nbsp;«продукт&nbsp;-&nbsp;клиент»</div>
      <div class="work__list">
        <div class="work__item work-item" v-for="(item, i) in card" :key="i">
          <div class="work-item__counter"><span></span></div>
          <div class="work-item__inner">
            <div class="work-item__descr">
              <div class="work-item__title">{{ item.title }}</div>
              <div class="work-item__subtitle">{{ item.subtitle }}</div>
              <ul class="work-item__list">
                <li v-for="(i) in item.list" :key="i">{{ i }}</li>
              </ul>
              <div v-if="item.text" class="work-item__text">{{ item.text }}</div>
            </div>
            <div class="work-item__img">
              <img :src="item.img" alt="svg">
            </div>
          </div>
        </div>

        <div class="work-item work__item work__item--green">
          <div class="work-item__counter"><TheSvg :type="'target'" /></div>
          <div class="work-item__inner">
            <div class="work-item__descr">
              <div class="work-item__title">Что в итоге?</div>
              <ul class="work-item__list">
                <li v-for="(i) in cardText" :key="i"><TheSvg :type="'marker'" />{{ i }}</li>
              </ul>
              <UITheButton :label="'Скачать программу'" class="btn btn-big btn-big__dark" />
            </div>
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
      card: [],
      cardText: ['Поймете риски и будущие сценарии развития событий в стране и своем рынке','Оцените вынужденные изменения в стратегии без убаюкивающего оптимизма','Определите приоритеты на ближайшие месяцы: когда риск неудачи меньше, чем риск бездействия',]
    }
  },
  async mounted() {
    const cards = []
    cards.push(
      {
        img: (await import("@/assets/img/practice/item1.svg")).default,
        title: 'Разбор полетов: анализируем стартовые данные',
        subtitle: 'Разбираем позитивный и негативный опыт:',
        list: ['На что мы смогли среагировать, а к чему оказались не готовы','На чем теперь зарабатываем, а какие цифры стали хуже','Какие решения сработали, а какие нет','Что позволяет усилиться бизнесу, а что — представляет угрозу его существованию',]
      },
      {
        img: (await import("@/assets/img/practice/item2.svg")).default,
        title: 'Что делать? Разрабатываем алгоритм действий',
        subtitle: 'Как и чем ответить, используя, что есть:',
        list: ['Используем по максимуму преимущества и наработки','«Живые» поставщики и клиенты','Потенциальные клиенты',]
      },
      {
        img: (await import("@/assets/img/practice/item3.svg")).default,
        title: 'Брейншторм – выбираем стратегию, подходящую вам именно сейчас',
        subtitle: 'Делаем шаг назад, продолжаем «как раньше» или разворачиваемся на 90°:',
        list: ['Упрощать или удешевлять?','Вынуть старую идею и отчаянно перезапустить?','Брать займы пока есть, надеясь на реструктуризацию и господдержку?'],
        text: 'И еще десяток идей, которые вы обоснуете вместе с ведущим, конкретизируете в виде системы действий, либо отложите на будущее'
      }
    )
    this.card = cards
	},
}
</script>

<style lang="scss">
.work {
  &__wrap {
    max-width: 1100px;
    padding: 0 20px;
    margin: 0 auto;
  }
  &__title {
  }
  &__subtitle {
    color: var(--grey2);
    font-size: 24px;
    font-weight: 600;
    text-align: center;
    max-width: 75%;
    margin: 0 auto 40px;
    @media(max-width: 767px) {
      font-size: 16px;
      max-width: 100%;
      margin: 0 auto 30px;
    }
  }
  &__item {
    &--green {
      background: linear-gradient(180deg, #00ADB0 0%, #0A7D80 100%);
      color: var(--white);
      position: relative;
      &::after {
        content: '';
        display: block;
        background-image: url('@/assets/img/line.svg');
        background-repeat: no-repeat;
        background-size: contain;
        background-position: 50% 50%;
        width: 430px;
        height: 360px;
        position: absolute;
        right: -180px;
        bottom: -14px;
        @media(max-width: 575px) {
          display: none;
        }
      }
      .work-item__inner {
        grid-template-columns: 0.8fr;
        @media(max-width: 767px) {
          grid-template-columns: 1fr;
        }
      }
      .work-item__title {
        color: var(--white);
      }
      .work-item__list li {
        display: flex;
        align-items: flex-start;
        margin-bottom: 15px;
        &::after {
          display: none;
        }
      }
      .work-item__list li svg {
        margin-right: 15px;
        flex: 0 0 25px;
      }
      .work-item__list li {
        padding-left: 0;
      }
      .work-item__list {
        margin-bottom: 35px;
      }
      .work-item__counter {
        &::after {
          display: none;
          @media(max-width: 767px) {
            display: block;
            background-color: var(--white);
          }
        }
        &::before {
          background-color: var(--white);
        }
      }
      .btn {
        @media(max-width: 577px) {
          padding-left: 0;
          padding-right: 0;
          width: 100%;
        }
      }
    }
  }
}
.work-item {
  background-color: var(--lightGreen2);
  border-radius: 15px;
  padding: 45px 50px 50px;
  margin-bottom: 25px;
  counter-increment: number;
  display: flex;
  overflow: hidden;
  @media(max-width: 767px) {
    padding: 30px 15px;
  }
  &:nth-child(1) {
    .work-item__counter::before {
      display: none;
    }
  }
  &__counter {
    width: 55px;
    height: 55px;
    background-color: var(--white);
    border-radius: 50%;
    border: solid 2px var(--lightGreen);
    position: relative;
    flex: 0 0 55px;
    max-width: 55px;
    margin-right: 30px;
    display: flex;
    justify-content: center;
    align-items: center;
    @media(max-width: 767px) {
      width: 35px;
      height: 35px;
      flex: 0 0 35px;
      margin-right: 15px;
      svg {
        max-width: 60%;
      }
    }
    &::after, &:before {
      content: '';
      display: block;
      width: 2px;
      position: absolute;
      background-color: var(--lightGreen);
    }
    &::before {
      top: -150px;
      height: 150px;
      @media(max-width: 7673px) {
        display: none;
      }
    }
    &::after {
      bottom: -500px;
      height: 500px;
      @media(max-width: 767px) {
        height: 1000px;
        bottom: -1000px;
      }
    }
    span {
      &::after {
        content: counter(number);
        font-size: 20px;
        color: var(--lightGreen);
      }
    }
  }
  &__inner {
    display: grid;
    grid-template-columns: 1fr 165px;
    gap: 30px;
    justify-content: space-between;
    width: 100%;
    @media(max-width: 767px) {
      grid-template-columns: 1fr;
      gap: 20px;
    }
  }
  &__descr {
  }
  &__title {
    font-size: 30px;
    color: var(--grey);
    font-weight: 500;
    margin-bottom: 25px;
    @media(max-width: 767px) {
      font-size: 18px;
      margin-bottom: 15px;
    }
  }
  &__subtitle {
    font-size: 18px;
    color: var(--grey2);
    font-weight: 400;
    margin-bottom: 15px;
    @media(max-width: 767px) {
      font-size: 14px;
      margin-bottom: 10px;
    }
  }
  &__list {
    li {
      position: relative;
      padding-left: 0.8em;
      margin-bottom: 10px;
      font-size: 18px;
      @media(max-width: 767px) {
        font-size: 14px;
      }
      &:last-child {
        margin-bottom: 0;
      }
      &::after {
        content: '';
        display: block;
        width: 6px;
        height: 6px;
        background-color: var(--lightGreen);
        border-radius: 50%;
        position: absolute;
        left: 0;
        top: 0.5em;
      }
    }
  }
  &__text {
    margin-top: 15px;
    column-rule-color: var(--grey);
    font-size: 18px;
    font-weight: 400;
  }
  &__img {
    text-align: center;
    @media(max-width: 767px) {
      text-align: left;
      img {
        max-width: 42%;
      }
    }
  }
}
</style>