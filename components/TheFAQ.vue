<template>
  <div class="wrapper">
    <div class="faq">
    <div class="faq__title title">Частые вопросы</div>
      <div class="faq__list">
        <div class="faq-item" 
          v-for="(item, i) in faq" :key="i"
          :class="(isOpenAccordionItem !== null && isOpenAccordionItem === i) ? 'open' : ''"
          @click="openAccordionItem(i)"  
        >
          <div class="faq-item__head">
            <div class="faq-item__title">{{ item.title }}</div>
            <span class="faq-item__cross" @click.stop="closeAccordionItem"></span>
          </div>
          <div class="faq-item__body" v-if="isOpenAccordionItem !== null && isOpenAccordionItem === i">{{ item.text }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isOpenAccordionItem: null,
      faq: [
        {
          title: 'Будем говорить только про краткосрочные перспективы?',
          text: 'Это первая программа АРБ ПРО, где разбираются краткосрочные перспективы, так как от того, как мы проживем эти несколько месяцев, будут зависеть сценарии дальнейшего развития бизнеса.'
        },
        {
          title: 'Почему программа практикума будет актуальна весь 2023 год?',
          text: 'Текущие изменения в Российской экономике - не временные. Уже понятно, что просто затаиться и переждать не получится. Самое подходящее время менять курс развития бизнеса - сегодня! Шансы на спасение бизнеса имеет только тот, кто принимает оперативные решения и держит руку на пульсе.'
        },
        {
          title: 'Для каких компаний эта программа?',
          text: 'Семинар-практикум для тех, кто сейчас ищет разворот, который поможет бизнесу пережить зиму и расцвести новыми красками весной.'
        },
      ]
    }
  },
  methods: {
    openAccordionItem(openItem) {
      this.isOpenAccordionItem = openItem
    },
    closeAccordionItem() {
      this.isOpenAccordionItem = null
    },
  }
}
</script>

<style lang="scss">
.faq {
  max-width: 990px;
  margin: 0 auto;
  &__title {}
}
.faq-item {
  background-color: var(--lightGreen2);
  border-radius: 5px;
  margin-bottom: 15px;
  padding: 20px 35px;
  cursor: pointer;
  &.open {
    cursor: default;
    .faq-item__cross {
      pointer-events: all;
      cursor: pointer;
      transform: rotate(135deg);
    }
  }
  &:last-child {
    margin-bottom: 0;
  }
  &__head {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  &__title {
    font-size: 24px;
    font-weight: 600;
    @media(max-width: 767px) {
      font-size: 16px;
    }
  }
  &__body {
    margin-top: 25px;
    font-size: 16px;
    @media(max-width: 767px) {
      font-size: 14px;
    }
  }
  &__cross {
    display: block;
    width: 45px;
    height: 45px;
    flex: 0 0 45px;
    border-radius: 50%;
    background-color: var(--white);
    pointer-events: none;
    transition: 0.3s;
    position: relative;
    margin-left: 10px;
    @media(max-width: 767px) {
      height: 40px;
      width: 40px;
      flex: 0 0 40px;
    }
    &::after, &::before {
      content: '';
      display: block;
      width: 50%;
      height: 2px;
      background-color: var(--grey);
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
    }
    &::before {
      transform: translate(-50%, -50%) rotate(90deg);
    }
  }
}
</style>