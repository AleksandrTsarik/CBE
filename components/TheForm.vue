<template>
  <div class="form">
    <div class="form__title title">Хотите уточнить условия участия?</div>
    <div class="form__subtitle">Пишите нам, мы проконсультируем по всем вопросам.</div>
    <form action="">
      <div class="form__inner">
        <div class="form__input">
          <UITheInput v-model:value="name" :type="'text'" :placeholder="'Укажите ваше ФИО полностью'" :name="'ФИО'"/>
          <UITheInput v-model:value="phone" :type="'tel'" :name="'Телефон'" />
          <UITheInput v-model:value="email" :type="'email'" :placeholder="'example@email.com'" :name="'e-mail'" />
        </div>
        <div class="form-checkbox">
          <label>
            <input type="checkbox" class="form-checkbox__input">
            <span class="form-checkbox__checked"></span>
            <div class="form-checkbox__check">Согласен с политикой обработки персональных данных</div>
          </label>
        </div>
        <div class="form__btn"><UITheButton :label="'Узнать стоимость'" class="btn btn-big btn-big__dark"  /></div>
      </div>
    </form>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss">
.form {
  &__title {
    text-align: left;
    color: var(--grey);
    margin-bottom: 10px;
  }
  &__subtitle {
    color: var(--grey3);
    font-size: 22px;
    font-weight: 500px;
    margin-bottom: 40px;
  }
  &__btn {
    @media(max-width: 767px) {
      text-align: center;
    }
  }
}
.form-checkbox {
  label {
    display: flex;
    align-items: center;
    margin: 20px 0 40px;
  }
  &__input {
    width: 0;
    height: 0;
    position: absolute;
    appearance: none;
  }
  &__checked {
    display: block;
    width: 24px;
    height: 24px;
    border: solid 1px var(--grey3);
    border-radius: 2px;
    cursor: pointer;
    margin-right: 10px;
    position: relative;
    background-color: var(--white);
    &::after {
      content: '';
      background-image: url('@/assets/img/checked.svg');
      background-repeat: no-repeat;
      background-position: center center;
      width: 12px;
      height: 9px;
      display: block;
      position: absolute;
      left: 50%;
      top: 50%;
      transform: translate(-50%, -50%);
      transition: 0.3s;
      opacity: 0;
    }
  }
  &__check {}
  &__input:checked ~ &__checked {
    &::after {
      opacity: 1;
    }
  }
}
</style>