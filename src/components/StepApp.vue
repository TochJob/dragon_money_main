<template>
  <div class="step">
    <div v-for="(item, index) of list" :key="index" class="step__item">
      <div v-html="item.svg"></div>
      <div class="step__wrapper">
        <p class="step__number">{{ index + 1 }}</p>
        <p class="step__text">{{ item.title }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';
const props = defineProps(['list']);
console.log('props', props);
</script>

<style lang="scss" scoped>
.step {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  gap: 9px;
  &.mobile {
    display: none;
  }
  &__item {
    position: relative;
    &:nth-child(3) {
      .step__wrapper {
        width: 88%;
      }
    }
  }
  &__text {
    color: #fff;
    font-size: 14px;
    font-weight: 500;
    text-transform: uppercase;
  }
  &__number {
    border-radius: 5.984px;
    background: #fe8f16;
    min-height: 34px;
    min-width: 34px;
    display: flex;
    justify-content: center;
    align-items: center;
    color: #fff;
    font-size: 23.936px;
    font-weight: 900;
    line-height: 23.936px; /* 100% */
    text-transform: uppercase;
  }
  &__wrapper {
    top: 50%;
    transform: translate(0, -52%);
    display: flex;
    align-items: center;
    gap: 10.5px;
    left: 6.75px;
    position: absolute;
    margin-left: 5px;
  }
}
@media (max-width: 1430.98px) {
  .step {
    flex-direction: column;
    align-items: flex-start;
    gap: 0px;
    margin: 96px 0;
    &.desc {
      display: none;
    }
    &.mobile {
      display: flex;
    }
    &__text {
      font-size: 17px;
    }
    &__item:nth-child(3) {
      .step__wrapper {
        width: 95%;
      }
    }
  }
}
@media (max-width: 576px) {
  .step{
    margin: 60px 0 190px;
  }
}

@media (max-width: 480px) {
  .step {
    margin: 30px 0 168px;
    &__text {
      font-size: 8px;
    }
    &__number {
      font-size: 14px;
      min-height: 21px;
      max-height: 21px;
      min-width: 21px;
      max-width: 21px;
    }
    &__item:nth-child(3) {
      .step__wrapper {
        width: 80%;
      }
    }
    &__wrapper {
      gap: 6px;
      margin-left: 0;
    }
  }
}
</style>
