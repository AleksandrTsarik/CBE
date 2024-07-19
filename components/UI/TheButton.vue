<template>
  <button
    :type="type"
    class="btn"
  >
    <span v-if="svg" v-html="svg"></span>
    {{ label }}
  </button>
</template>

<script>
export default {
  props: {
    label: {
      label: String,
      default: '',
      require: true
    },
    type: {
      type: String,
      dafault: ''
    },
    svg: {
      type: String,
      dafault: ''
    }
  }
}
</script>

<style lang="scss">
  .btn {
    border: solid 1px transparent;
    cursor: pointer;
    transition: 0.3s;
    display: inline-block;
    &:active {
      @media(max-width: 1023px) {
        background-color: tomato;
      }
    } 
  }
  .btn-big {
    border-radius: 8px;
    font-size: 18px;
    line-height: 100%;
    padding: 15px 52px;
    transition: 0.3s;
    &__dark {
      background-color: var(--red);
      color: var(--white);
      font-weight: 500;
      &:hover {
        @media(min-width: 1024px) {
          background-color: lighten(#DB1515, 10%);
        }
      }
    }
    &__light {
      border-color: var(--red);
      color: var(--red);
      &:hover {
        @media(min-width: 1024px) {
          background-color: lighten(#DB1515, 40%);
        }
      }
    }
  }
  .btn-small {
    font-size: 14px;
    font-weight: 500;
    border-radius: 4px;
    padding: 4px 15px;
    &__dark {
      background-color: var(--lightGreen);
      color: var(--white);
      &:hover {
        @media(min-width: 1024px) {
          background-color: lighten(#045C5E, 10%);
        }
      }
    }
    &__light {
      border-color: var(--lightGreen);
      color: var(--lightGreen);
      &:hover {
        @media(min-width: 1024px) {
          background-color: rgba(#05a0a2, 0.1);
        }
      }
    }
  }
</style>