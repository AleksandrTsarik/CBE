<template>
    <div class="about">
      <span></span>
      <div class="wrapper">
      <div class="about__inner">
        <div class="about__row">Программу ведет руководитель стратегического консалтинга ГК «Институт Тренинга - АРБ Про»</div>
        <div class="about__title title">Демид Голиков</div>
        <div class="about__descr">Эксперт и консультант по направлениям: стратегическое планирование, концепции и бизнес-идеи, фасилитация стратегических сессий. C 2013 ежегодно участвует в Глобальном саммите директоров по стратегическому планированию.</div>
        <div class="about__competency">
          <p>Компетенции:</p>
          <ul>
            <li v-for="i in list" :key="i">{{ i }}</li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      list: ['Независимый директор ряда российских компаний','Магистр по экономике (MPhil) Оксфордского Университета, Великобритания','Сертифицированный специалист по фасилитации: Leadership Strategies Institute (США), Pinpoint Facilitation Limited, (Великобритания) и управлению изменениями: CMC Partnership (Великобритания)','Более 20 проектов в год по стратегическому управлению и планированию','Более 50 проектов по стратегическому планирования для частных компаний и холдингов из разных отраслей – инжиниринг, строительство, FMCG, энергетика, автокомпоненты и т.д. (Toyota, Протэк, Faberlic, LEDEL, РС «Монетка», Jumbo Toys, ГК «Баусервис», Splat, «МН-Холдинг», Dental Kosmetik, «Эколенд», Finn Flare, Манго Телеком, Деловой Квартал и др.)',]
    }
  }
}
</script>

<style lang="scss">
.about {
  background-image: url('@/assets/img/bg-big.webp');
  background-repeat: no-repeat;
  background-position: 50% 50%;
  background-size: cover;
  width: 100%;
  border-radius: 30px;
  text-align: left;
  padding: 75px 0 75px;
  position: relative;
  overflow: hidden;
  background-color: #E6F5F5;
  @media(max-width: 767px) {
    padding: 40px 0;
    background-image: url('@/assets/img/bg-big-small.webp');
    background-position: bottom 0 right 0;
    background-size: contain;
  }
  span {
    display: block;
    background-image: url('@/assets/img/man-big.webp');
    background-position: 50% 50%;
    background-repeat: no-repeat;
    background-size: auto 100%;
    width: 780px;
    padding-bottom: 45%;
    position: absolute;
    right: -190px;
    bottom: 0;
    @media(max-width: 1440px) {
      padding-bottom: 55%;
    }
    @media(max-width: 1023px) {
      padding-bottom: 100%;
      border-radius: 15px;
      overflow: hidden;
      &::before {
        content: '';
        display: block;
        width: 100%;
        height: 100%;
        position: absolute;
        left: 0;
        top: 0;
        overflow: hidden;
        background: linear-gradient(0.00deg, rgb(233, 246, 246) 0%,rgba(234, 246, 246, 0.84) 13.182%,rgba(234, 246, 246, 0.65) 28.393%,rgba(235, 247, 247, 0.38) 44.104%,rgba(236, 247, 247, 0.18) 56.975%,rgba(237, 247, 247, 0) 68.817%);
        border-radius: 15px;
      }
    }
    @media(max-width: 767px) {
      height: 465px;
      width: 100%;
      padding-bottom: 0;
      right: auto;
      left: 0;
      &::before {
        display: none;
      }
    }
  }
  &__inner {
    max-width: 46%;
    @media(max-width: 767px) {
      max-width: 100%;
      padding-bottom: 455px;
    }
  }
  &__row {
    color: var(--darkGreen);
    font-size: 20px;
    font-weight: 500;
    margin-bottom: 15px;
    @media(max-width: 767px) {
      font-size: 13px;
    }
  }
  &__title {
    text-align: left;
  }
  &__descr {
    color: var(--grey);
    font-size: 20px;
    font-weight: 500;
    margin-bottom: 45px;
    @media(max-width: 767px) {
      font-stretch: 16px;
    }
  }
  &__competency {
    p {
      color: var(--grey);
      font-size: 24px;
      font-weight: 600;
      margin-bottom: 25px;
      @media(max-width: 767px) {
        font-size: 18px;
        margin-bottom: 15px;
      }
    }
    li {
      position: relative;
      padding-left: 15px;
      font-stretch: 18px;
      font-weight: 400;
      margin-bottom: 15px;
      @media(max-width: 767px) {
        font-stretch: 14px;
      }
      &:last-child {
        margin-bottom: 0;
      }
      &::after {
        content: '';
        display: block;
        position: absolute;
        left: 0;
        top: 0.4em;
        width: 5px;
        height: 5px;
        background-color: var(--lightGreen);
        transform: rotate(45deg);
      }
    }
  }
}
</style>