<script setup>
import BMainLine from "@/components/svg/BMainLine.vue";
// import BSecondLine from "@/components/svg/BSecondLine.vue";

const steps = [
  {
    title: "Зарегистрируйся",
    svg: '<svg xmlns="http://www.w3.org/2000/svg" width="221" height="53" viewBox="0 0 221 53" fill="none"><path d="M195.02 1.14355H7.95214C4.64734 1.14355 1.96826 3.82262 1.96826 7.12743V45.5402C1.96826 48.845 4.64733 51.524 7.95213 51.524H195.02C196.645 51.524 198.2 50.8634 199.327 49.6939L217.849 30.4875C220.084 28.1695 220.084 24.4981 217.849 22.1801L199.327 2.97372C198.2 1.8042 196.645 1.14355 195.02 1.14355Z" stroke="white" stroke-width="2.24395"/></svg>',
  },
  {
    title: "сделай депозит",
    svg: '<svg xmlns="http://www.w3.org/2000/svg" width="221" height="53" viewBox="0 0 221 53" fill="none">  <path d="M195.02 1.14355H7.95214C4.64734 1.14355 1.96826 3.82262 1.96826 7.12743V45.5402C1.96826 48.845 4.64733 51.524 7.95213 51.524H195.02C196.645 51.524 198.2 50.8634 199.327 49.6939L217.849 30.4875C220.084 28.1695 220.084 24.4981 217.849 22.1801L199.327 2.97372C198.2 1.8042 196.645 1.14355 195.02 1.14355Z" stroke="white" stroke-width="2.24395"/></svg>',
  },
  {
    title: "выполни все задания во вкладке «бонус»",
    svg: '<svg xmlns="http://www.w3.org/2000/svg" width="257" height="54" viewBox="0 0 257 54" fill="none">  <path d="M228.023 1.86816H7.88524C4.58044 1.86816 1.90137 4.54723 1.90137 7.85204V46.2648C1.90137 49.5696 4.58043 52.2487 7.88523 52.2487H228.023C229.487 52.2487 230.901 51.7115 231.996 50.739L253.623 31.5326C256.304 29.1521 256.304 24.9647 253.623 22.5842L231.996 3.37781C230.901 2.40529 229.487 1.86816 228.023 1.86816Z" stroke="white" stroke-width="2.24395"/></svg>',
  },
  {
    title: "получи бонус!",
    svg: '<svg xmlns="http://www.w3.org/2000/svg" width="192" height="54" viewBox="0 0 192 54" fill="none">  <path d="M168.39 1.64062H7.69262C4.38781 1.64062 1.70874 4.31969 1.70874 7.6245V46.0372C1.70874 49.342 4.3878 52.0211 7.6926 52.0211H168.39C170.163 52.0211 171.845 51.2347 172.982 49.8741L189.03 30.6677C190.886 28.4465 190.886 25.2152 189.03 22.994L172.982 3.78765C171.845 2.42699 170.163 1.64062 168.39 1.64062Z" stroke="white" stroke-width="2.24395"/></svg>',
  },
];
</script>

<template>
  <BMainLine class="line line__first" />
  <BMainLine class="line line__second" />
  <BMainLine class="line line__third" />

  <section>
    <div class="main">
      <div class="main__box">
        <img src="@/assets/img/logo.png" alt="logo" />
        <h1 class="main__title">бонус</h1>
        <div class="wrapper">
          <p class="main__text">до</p>
          <p class="main__text special">500 монет</p>
          <p class="main__text">на игровой баланс</p>
        </div>
        <button class="main__button button">получить бонус</button>
      </div>
      <img class="main__logo" src="@/assets/img/main.png" alt="main logo" />
    </div>
    <div class="step">
      <div v-for="(item, index) of steps" :key="index" class="step__item">
        <div v-html="item.svg"></div>
        <div class="step__wrapper">
          <p class="step__number">{{ index + 1 }}</p>
          <p class="step__text">{{ item.title }}</p>
        </div>
      </div>
    </div>
  </section>
  <!-- <BSecondLine /> -->
</template>
<style lang="scss">
@import "@/assets/scss/base.scss";
@import "@/assets/scss/animation.scss";
#app {
  background: radial-gradient(
    124.98% 61.75% at 36.24% 50%,
    #373c55 33.85%,
    #181a25 100%
  );
  overflow: hidden;
  // height: 100vh;
  position: relative;
  z-index: -2;

  .line {
    z-index: -1;
    width: 1200px;
    &__first {
      top: -50%;
      right: -8%;
      transform: translate(42%, -30%);
      animation: first__line 1s ease-out 1 normal forwards;
    }
    &__second {
      top: -16%;
      right: -16%;
      width: 1300px;
      animation: first__line 1.5s ease-out 1 normal forwards;
    }
    &__third {
      top: -48%;
      width: 1000px;
      right: -13%;
      animation: first__line 0.5s ease-out 1 normal forwards;
    }
  }
  .wrapper {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    width: 100%;
  }

  .main {
    margin-top: 160px;
    margin-bottom: 220px;
    &__title {
      color: #fe8f16;
      font-size: 168px;
      font-weight: 900;
      text-transform: uppercase;
    }
    &__box {
      display: flex;
      flex-direction: column;
      align-items: center;
      max-width: 555px;
    }
    &__text {
      color: #fff;
      font-family: Exo 2;
      font-size: 24px;
      line-height: 90%;
      font-weight: 400;
      text-transform: uppercase;
      &.special {
        font-size: 56px;
        width: 100%;
        font-weight: 900;
        display: flex;
        align-items: flex-end;
        justify-content: center;
      }
    }
    &__logo {
      position: absolute;
      right: 10%;
      top: 20%;
      width: 684px;
    }
    &__button {
      color: #fff;
      font-size: 24px;
      font-weight: 900;
      text-transform: uppercase;
      padding: 24px 61px;
      border-radius: 8px;
      background: #fe8f16;
      margin-top: 180px;
    }
  }

  .step {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    gap: 9px;
    &__item {
      position: relative;
      &:nth-child(3){
        .step__wrapper{
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
      transform: translate(0, -50%);
      display: flex;
      align-items: center;
      gap: 10.5px;
      left: 6.75px;
      position: absolute;
    }
  }
}

section,
header,
footer {
  padding: 0 15px;
}

@media (min-width: 575.98px) {
  section,
  header,
  footer {
    padding: 0 calc(35vw - 270px);
  }
}

@media (min-width: 767.98px) {
  section,
  header,
  footer {
    padding: 0 calc(35vw - 360px);
  }
}

@media (min-width: 991.98px) {
  section,
  header,
  footer {
    padding: 0 calc(35vw - 480px);
  }
}

@media (min-width: 1199.98px) {
  section,
  header,
  footer {
    padding: 0 calc(35vw - 590px);
  }
}
</style>
