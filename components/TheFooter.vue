<template>
  <footer class="footer">
    <div class="footer__inner wrapper">
      <div class="footer-info">
        <div class="footer-info__item">
          <div class="footer-info__title">ЦБО</div>
          <ul class="footer-info__block">
            <li class="footer-info__name" v-for="(item, i) in linkItem" :key="i">
              <NuxtLink :to="item.url">{{ item.name }}</NuxtLink>
            </li>
          </ul>
        </div>
        <div class="footer-info__item">
          <div class="footer-info__item-nav">
            <div class="footer-info__title">Информация</div>
            <ul class="footer-info__block">
              <li class="footer-info__name" v-for="(item, i) in linkItem2" :key="i">
                <NuxtLink :to="item.url">{{ item.name }}</NuxtLink>
              </li>
            </ul>
          </div>
          <div class="footer-info__item-descr">
            <div class="footer-info__phone">
              <NuxtLink to="tel:88007001996">8 800 700 1996</NuxtLink>
              <p>Звонок бесплатный</p>
            </div>
            <div class="footer-info__network">
              <TheNetwork v-for="n in network" :type="n" :key="n" />
            </div>
            <NuxtLink to="#" class="footer-info__subscription">5 причин подписаться</NuxtLink>
          </div>
        </div>
      </div>
      <div class="footer-strip">
        <div class="footer-strip__logo"><TheNetwork :type="'logo'" /></div>
        <div class="footer-strip__row">© Группа Компаний «ЦБО» Центр Бизнес-Образования | 1996 — 2022. Копирование любых материалов с сайта запрещено.</div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  data() {
    return {
      linkItem: [
        {
          name: 'МБА',
          url: '#'
        },
        {
          name: 'Курсы',
          url: '#'
        },
        {
          name: 'Корпоративное обучение',
          url: '#'
        },
        {
          name: 'Молодежная Бизнес-Лига',
          url: '#'
        },
        {
          name: 'Клуб ЦБО',
          url: '#'
        },
        {
          name: 'Партнерство',
          url: '#'
        },
        {
          name: 'О компании',
          url: '#'
        },
        {
          name: 'Работа в ЦБО',
          url: '#'
        },
        
      ],
      linkItem2: [
        {
          name: 'НОЧУ ДПО “ЦБО”',
          url: '#'
        },
        {
          name: 'Оплата банковскими картами',
          url: '#'
        },
        {
          name: 'Реквизиты',
          url: '#'
        },
        {
          name: 'Политика конфиденциальности',
          url: '#'
        },
        
      ],
      network: ['instagram','facebook','twitter','medium','telegram','youtube']
    }
  }
}
</script>

<style lang="scss">
  .footer {
    background-color: rgba(#80899E12, 0.07);
    padding: 30px 0;
  }
  .footer-info{
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
    border-bottom: solid 1px #E5E7EB;
    padding-bottom: 30px;
    margin-bottom: 30px;
    @media(max-width: 1023px) {
      grid-template-columns: 1fr;
      max-width: 80%;
      margin: 0 auto;
      text-align: center;
    }
    &__item {
      &:first-child {
        ul {
          column-count: 2;
          @media(max-width: 1023px) {
            column-count: 1;
          }
        }
        li {
        }
      }
      &:last-child {
          display: grid;
          grid-template-columns: 1fr 1fr;

          @media(max-width: 1023px) {
            grid-template-columns: 1fr;
          }
        }
    }
    &__title {
      color: var(--block);
      font-size: 16px;
      font-weight: 500;
      margin-bottom: 15px;
    }
    &__name {
      margin-bottom: 15px;
      &:hover {
        @media(min-width: 1024px) {
          a {
            color: var(--lightGreen);
            border-color: var(--lightGreen);
          }
        }
      }
      a {
        color: var(--green2);
        font-size: 16px;
        font-weight: 500;
        transition: 0.3s;
        border-bottom: solid 1px transparent;
      }
    }
    &__phone {
      margin-bottom: 40px;
      text-align: right;
      @media(max-width: 1023px) {
        text-align: center;
      }
      a {
        color: var(--green2);
        font-size: 24px;
        font-weight: 600;
      }
      p {
        color: var(--block);
        font-size: 12px;
        font-weight: 400;
      }
    }
    &__network {
      justify-content: space-between;
      display: flex;
      align-items: center;
      margin-bottom: 15px;
      @media(max-width: 1023px) {
        margin: 0 auto;
        max-width: 50%;
        flex-wrap: wrap;
        text-align: center;
      }
      a{
        @media(max-width: 1023px) {
          flex: 0 0 33.33%;
          max-width: 33.333%;
          margin-bottom: 20px;
          text-align: center;
        }
        &:hover{
        @media(min-width: 1024px) {

          filter: drop-shadow(0 0  4px rgba(black , 0.2));
        }
      }
      }

    }
    &__subscription {
      font-size: 16px;
      font-weight: 500;
      color: var(--green2);
      display: block;
      text-align: right;
      @media(max-width: 1023px) {
        text-align: center;
      }
    }
  }
  .footer-strip {
    display: flex;
    align-items: center;
    justify-content: space-between;
    &__logo {
      flex: 0 0 65px;
      max-width: 65px;
      a {
        display: block;
      }
      svg {
        max-width: 65px;
      }
    }
    &__row {
      columns: var(--row);
      font-size: 12px;
      font-weight: 400;
    }
  }
</style>