<template>
  <div class="wrapper">
    <div class="part">
      <TheForm />
      <div class="part__inner">
        <div class="part__photo">
          <img src="@/assets/img/user.png" alt="photo">
        </div>
        <div class="part__descr">
          <div class="part__name">Шуравина Надежда</div>
          <div class="part__place">Ведущий специалист Бизнес-школы ЦБО</div>
          <div class="part__phone">+7 (343) 38 50 500 (доб. 410)</div>
          <NuxtLink to="mailto:m02@cbo.ru" class="part__email">m02@cbo.ru</NuxtLink>
        </div>
      </div>
    </div>
    
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss">
  .part {
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 95px;
    @media(max-width: 767px) {
      grid-template-columns: 1fr; 
      gap: 40px;
    }
    &__inner {
      max-width: 295px;
      @media(max-width: 767px) {
        text-align: center;
        margin: 0 auto;
      }
    }
    &__photo {
      max-width: 295px;
      max-height: 295px;
      border-radius: 50%;
      left: 1025px;
      box-shadow: 0px 4px 10px 0px rgba(0, 0, 0, 0.25);
      overflow: hidden;
      margin-bottom: 20px;
      @media(max-width: 767px) {
        max-width: 200px;
        max-height: 200px;
        margin: 0 auto 20px;
      }
      img {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
    &__descr {
      text-align: center;
    }
    &__name {
      color: var(--grey);
      font-size: 20px;
      font-weight: 600;
      line-height: 120%;
      margin-bottom: 5px;
    }
    &__place {
      color: var(--block);
      font-size: 16px;
      font-weight: 400;
      max-width: 60%;
      margin: 0 auto 15px;
    }
    &__phone {
      color: var(--grey);
      font-size: 16px;
      font-weight: 600;
      margin-bottom: 10px;
    }
    &__email {
      color: var(--lightGreen);
      font-size: 16px;
      font-weight: 600;
    }
  }
</style>