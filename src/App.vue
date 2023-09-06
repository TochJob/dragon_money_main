<script setup>
import BMainLine from '@/components/svg/BMainLine.vue';
import FooterApp from '@/components/FooterApp.vue';
import BSecondLine from '@/components/svg/BSecondLine.vue';
import StepApp from '@/components/StepApp.vue';

import { ref, onMounted, onBeforeUnmount } from 'vue';

const screenWidth = ref(window.innerWidth);
const screenHeight = ref(window.innerHeight);

// Обновление размеров при изменении размеров окна
const updateScreenSize = () => {
  screenWidth.value = window.innerWidth;
  screenHeight.value = window.innerHeight;
};

// Добавляем слушатель при монтировании компонента
onMounted(() => {
  window.addEventListener('resize', updateScreenSize);
});

// Удаляем слушатель при размонтировании компонента
onBeforeUnmount(() => {
  window.removeEventListener('resize', updateScreenSize);
});

const steps = [
  {
    title: 'Зарегистрируйся',
    svg: '<svg xmlns="http://www.w3.org/2000/svg" width="221" height="53" viewBox="0 0 221 53" fill="none"><path d="M195.02 1.14355H7.95214C4.64734 1.14355 1.96826 3.82262 1.96826 7.12743V45.5402C1.96826 48.845 4.64733 51.524 7.95213 51.524H195.02C196.645 51.524 198.2 50.8634 199.327 49.6939L217.849 30.4875C220.084 28.1695 220.084 24.4981 217.849 22.1801L199.327 2.97372C198.2 1.8042 196.645 1.14355 195.02 1.14355Z" stroke="white" stroke-width="2.24395"/></svg>',
  },
  {
    title: 'сделай депозит',
    svg: '<svg xmlns="http://www.w3.org/2000/svg" width="221" height="53" viewBox="0 0 221 53" fill="none">  <path d="M195.02 1.14355H7.95214C4.64734 1.14355 1.96826 3.82262 1.96826 7.12743V45.5402C1.96826 48.845 4.64733 51.524 7.95213 51.524H195.02C196.645 51.524 198.2 50.8634 199.327 49.6939L217.849 30.4875C220.084 28.1695 220.084 24.4981 217.849 22.1801L199.327 2.97372C198.2 1.8042 196.645 1.14355 195.02 1.14355Z" stroke="white" stroke-width="2.24395"/></svg>',
  },
  {
    title: 'выполни все задания во вкладке «бонус»',
    svg: '<svg xmlns="http://www.w3.org/2000/svg" width="257" height="54" viewBox="0 0 257 54" fill="none">  <path d="M228.023 1.86816H7.88524C4.58044 1.86816 1.90137 4.54723 1.90137 7.85204V46.2648C1.90137 49.5696 4.58043 52.2487 7.88523 52.2487H228.023C229.487 52.2487 230.901 51.7115 231.996 50.739L253.623 31.5326C256.304 29.1521 256.304 24.9647 253.623 22.5842L231.996 3.37781C230.901 2.40529 229.487 1.86816 228.023 1.86816Z" stroke="white" stroke-width="2.24395"/></svg>',
  },
  {
    title: 'получи бонус!',
    svg: '<svg xmlns="http://www.w3.org/2000/svg" width="192" height="54" viewBox="0 0 192 54" fill="none">  <path d="M168.39 1.64062H7.69262C4.38781 1.64062 1.70874 4.31969 1.70874 7.6245V46.0372C1.70874 49.342 4.3878 52.0211 7.6926 52.0211H168.39C170.163 52.0211 171.845 51.2347 172.982 49.8741L189.03 30.6677C190.886 28.4465 190.886 25.2152 189.03 22.994L172.982 3.78765C171.845 2.42699 170.163 1.64062 168.39 1.64062Z" stroke="white" stroke-width="2.24395"/></svg>',
  },
];

const steps1024 = [
  {
    title: 'Зарегистрируйся',
    svg: '<svg xmlns="http://www.w3.org/2000/svg" width="252" height="65" viewBox="0 0 252 65" fill="none"><path d="M221.714 1.38037H8.86053C4.79313 1.38037 1.49585 4.67765 1.49585 8.74504V56.0216C1.49585 60.089 4.79312 63.3863 8.86051 63.3863H221.714C223.808 63.3863 225.803 62.4946 227.201 60.9342L248.365 37.2959C250.869 34.4994 250.869 30.2672 248.365 27.4707L227.201 3.83245C225.803 2.2721 223.808 1.38037 221.714 1.38037Z" stroke="white" stroke-width="2.76175"/></svg>',
  },
  {
    title: 'сделай депозит',
    svg: `<svg xmlns="http://www.w3.org/2000/svg" width="271" height="65" viewBox="0 0 271 65" fill="none">
  <path d="M239.095 1.38567H8.86053C4.79313 1.38567 1.49585 4.68294 1.49585 8.75034V56.0269C1.49585 60.0943 4.79312 63.3916 8.86052 63.3916H239.095C241.095 63.3916 243.008 62.5785 244.396 61.1391L267.191 37.5008C269.943 34.6479 269.943 30.1294 267.191 27.2764L244.396 3.63814C243.008 2.19876 241.095 1.38567 239.095 1.38567Z" stroke="white" stroke-width="2.76175"/>
</svg>`,
  },
  {
    title: 'выполни все задания во вкладке «бонус»',
    svg: `<svg xmlns="http://www.w3.org/2000/svg" width="316" height="65" viewBox="0 0 316 65" fill="none">
  <path d="M279.796 1.39116H8.86053C4.79313 1.39116 1.49585 4.68843 1.49585 8.75583V56.0324C1.49585 60.0998 4.79315 63.3971 8.86054 63.3971H279.796C281.598 63.3971 283.338 62.736 284.686 61.5391L311.304 37.9008C314.603 34.9709 314.603 29.8173 311.304 26.8875L284.686 3.24916C283.338 2.05223 281.598 1.39116 279.796 1.39116Z" stroke="white" stroke-width="2.76175"/>
</svg>`,
  },
  {
    title: 'получи бонус!',
    svg: `<svg xmlns="http://www.w3.org/2000/svg" width="236" height="65" viewBox="0 0 236 65" fill="none">
  <path d="M206.639 1.39686H8.86053C4.79313 1.39686 1.49585 4.69413 1.49585 8.76153V56.0381C1.49585 60.1055 4.79314 63.4028 8.86053 63.4028H206.64C208.822 63.4028 210.892 62.435 212.291 60.7604L232.043 37.1221C234.327 34.3883 234.327 30.4114 232.043 27.6776L212.291 4.03931C210.892 2.36468 208.822 1.39686 206.639 1.39686Z" stroke="white" stroke-width="2.76175"/>
</svg>`,
  },
];
const stepsMob = [
  {
    title: 'Зарегистрируйся',
    svg: `<svg xmlns="http://www.w3.org/2000/svg" width="128" height="33" viewBox="0 0 128 33" fill="none">
  <path d="M112.294 1.00037H5.14673C3.09926 1.00037 1.43945 2.66017 1.43945 4.70764V28.506C1.43945 30.5535 3.09926 32.2133 5.14673 32.2133H112.294C113.348 32.2133 114.353 31.7644 115.056 30.9789L125.71 19.0798C126.97 17.672 126.97 15.5416 125.71 14.1339L115.056 2.23471C114.353 1.44925 113.348 1.00037 112.294 1.00037Z" stroke="white" stroke-width="1.39023"/>
</svg>`,
  },
  {
    title: 'сделай депозит',
    svg: `<svg xmlns="http://www.w3.org/2000/svg" width="137" height="34" viewBox="0 0 137 34" fill="none">
  <path d="M121.044 1.21283H5.14673C3.09926 1.21283 1.43945 2.87264 1.43945 4.92011V28.7185C1.43945 30.7659 3.09926 32.4257 5.14673 32.4257H121.044C122.05 32.4257 123.013 32.0164 123.712 31.2919L135.187 19.3927C136.572 17.9566 136.572 15.682 135.187 14.2459L123.712 2.3467C123.013 1.62213 122.05 1.21283 121.044 1.21283Z" stroke="white" stroke-width="1.39023"/>
</svg>`,
  },
  {
    title: 'выполни все задания во вкладке «бонус»',
    svg: `<svg xmlns="http://www.w3.org/2000/svg" width="160" height="34" viewBox="0 0 160 34" fill="none">
  <path d="M141.532 1.4256H5.14673C3.09926 1.4256 1.43945 3.0854 1.43945 5.13288V28.9312C1.43945 30.9787 3.09927 32.6385 5.14674 32.6385H141.532C142.439 32.6385 143.315 32.3057 143.993 31.7032L157.392 19.804C159.053 18.3292 159.053 15.7349 157.392 14.2601L143.993 2.36089C143.315 1.75837 142.439 1.4256 141.532 1.4256Z" stroke="white" stroke-width="1.39023"/>
</svg>`,
  },
  {
    title: 'получи бонус!',
    svg: `<svg xmlns="http://www.w3.org/2000/svg" width="120" height="34" viewBox="0 0 120 34" fill="none">
  <path d="M104.706 1.63831H5.14673C3.09926 1.63831 1.43945 3.29811 1.43945 5.34558V29.144C1.43945 31.1914 3.09926 32.8512 5.14673 32.8512H104.706C105.804 32.8512 106.846 32.364 107.551 31.521L117.493 19.6219C118.643 18.2457 118.643 16.2438 117.493 14.8677L107.551 2.96848C106.846 2.1255 105.804 1.63831 104.706 1.63831Z" stroke="white" stroke-width="1.39023"/>
</svg>`,
  },
];
</script>

<template>
  <section class="land">
    <BMainLine class="line line__first" />
    <BMainLine class="line line__second" />
    <BMainLine class="line line__third" />
    <BSecondLine class="line line__bg line__bg-first" />
    <BSecondLine class="line line__bg line__bg-second" />
    <BSecondLine class="line line__bg line__bg-third" />
    <BSecondLine class="line line__bg line__bg-forth" />
    <img class="main__logo" src="@/assets/img/main.png" alt="main logo" />

    <div class="main">
      <div class="main__box">
        <img class="main__icon" src="@/assets/img/logo.png" alt="logo" />
        <h1 class="main__title">бонус</h1>
        <div class="wrapper">
          <p class="main__text">до</p>
          <p class="main__text special">500 монет</p>
          <p class="main__text">на игровой баланс</p>
        </div>
        <StepApp class="mobile" :list="screenWidth <= 480 ? stepsMob : steps1024" />

        <button class="main__button button">получить бонус</button>
      </div>
    </div>
    <StepApp class="desc" :list="steps" />
  </section>
  <FooterApp />
  <!-- <BSecondLine /> -->
</template>
<style lang="scss">
@import '@/assets/scss/base.scss';
@import '@/assets/scss/animation.scss';
#app {
  // background: radial-gradient(124.98% 61.75% at 36.24% 50%, #202331 33.85%, #181a25 100%);
  background-image: url('@/assets/img/background.png');
  overflow: hidden;
  position: relative;
}
section,
header,
footer {
  padding: 0 calc(35vw - 414px);
}

.land {
  position: relative;
  overflow: hidden;
}
.line {
  width: 1200px;
  position: absolute;

  &__first {
    top: -53%;
    right: -14%;
    transform: translate(42%, -30%);
    animation: first__line 1s ease-out 1 normal forwards;
  }
  &__second {
    top: -17%;
    right: -21%;
    width: 1300px;
    animation: first__line 1.5s ease-out 1 normal forwards;
  }
  &__third {
    top: -44%;
    width: 1000px;
    right: -17%;
    animation: first__line 0.5s ease-out 1 normal forwards;
  }
  &__bg {
    &-first {
      top: -100%;
      right: -100%;
      animation: bg__line 6s ease-out 1.5s infinite normal forwards;
    }
    &-second {
      top: -100%;
      right: 0%;
      animation: bg__line 5s ease-out 1.5s infinite normal forwards;
    }
    &-third {
      top: -100%;
      right: -70%;
      animation: bg__line 5s ease-out 1.5s infinite normal forwards;
    }
    &-forth {
      top: -100%;
      right: -50%;
      animation: bg__line 4s ease-out 1.5s infinite normal forwards;
    }
  }
}

.main {
  position: relative;
  padding: 160px 0 220px;
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
    font-family: 'Exo 2';
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
    right: 6%;
    top: 12%;
    width: 684px;
  }
  &__button {
    color: #fff;
    font-size: 24px;
    font-weight: 900;
    font-family: 'Exo 2';
    text-transform: uppercase;
    padding: 26px 53px;
    border-radius: 8px;
    background: #fe8f16;
    margin-top: 180px;
    cursor: pointer;
    border: none;
  }
}

.wrapper {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  width: 100%;
}

@media (max-width: 1700.98px) {
  .line {
    width: 1200px;
    position: absolute;

    &__first {
      top: -53%;
      right: -29%;
      transform: translate(42%, -30%);
      animation: first__line 1s ease-out 1 normal forwards;
    }
    &__second {
      top: -17%;
      right: -34%;
      width: 1300px;
      animation: first__line 1.5s ease-out 1 normal forwards;
    }
    &__third {
      top: -44%;
      width: 1000px;
      right: -30%;
      animation: first__line 0.5s ease-out 1 normal forwards;
    }
  }
}

@media (max-width: 1430.98px) {
  section,
  header,
  footer {
    padding: 0 0 0 calc(35vw - 258px);
  }

  .land {
    padding-bottom: 100px;
  }

  .line {
    &__first {
      width: 765px;
      top: -6%;
      right: -23%;
    }
    &__second {
      width: 855px;
      top: 11%;
      right: -36%;
    }
    &__third {
      width: 646px;
      top: -4%;
      right: -29%;
    }
  }

  .main {
    margin: 0;
    padding: 81px 0 0 0;
    &__title {
      margin-top: 71px;
    }
    &__logo {
      width: 435px;
      right: 0;
      top: unset;
      bottom: 40px;
    }
    &__button {
      margin-top: 0;
      align-self: flex-start;
    }
  }
}
@media (max-width: 992px) {
  section,
  header,
  footer {
    padding: 0 calc(35vw - 255px);
  }
  .main {
    &__logo {
      width: 380px;
      bottom: 65px;
    }
  }
  .line {
    &__first {
      width: 765px;
      top: -6%;
      right: -40%;
    }
    &__second {
      width: 855px;
      top: 14%;
      right: -58%;
    }
    &__third {
      width: 646px;
      top: -0%;
      right: -44%;
    }
    &__bg {
      width: 800px;
      &-first {
        top: -60%;
        right: -150%;
        animation: bg__line 6s ease-out 1.5s infinite normal forwards;
      }
      &-second {
        top: -70%;
        right: -110%;
        animation: bg__line 5s ease-out 1.5s infinite normal forwards;
      }
      &-third {
        top: -100%;
        right: -70%;
        animation: bg__line 5s ease-out 1.5s infinite normal forwards;
      }
      &-forth {
        top: -100%;
        right: -50%;
        animation: bg__line 4s ease-out 1.5s infinite normal forwards;
      }
    }
  }
}
@media (max-width: 768px) {
  section,
  header,
  footer {
    padding: 0 calc(50vw - 280px);
  }
  .land {
    padding-bottom: 0px;
  }
  .line {
    &__first {
      width: 400px;
      top: 17%;
      right: -10%;
    }
    &__second {
      width: 420px;
      top: 24%;
      right: -27%;
    }
    &__third {
      width: 350px;
      top: 18%;
      right: -17%;
    }
    &__bg {
      &-first {
        top: -100%;
        width: 280px;
        right: -50%;
        animation: bg__line 10s ease-out 1.5s infinite normal forwards;
      }
      &-second {
        top: -70%;
        width: 280px;
        right: 0%;
        animation: bg__line 9s ease-out 1.5s infinite normal forwards;
      }
      &-third {
        width: 280px;
        top: -50%;
        right: -70%;
        animation: bg__line 9s ease-out 1.5s infinite normal forwards;
      }
      &-forth {
        width: 280px;
        top: -50%;
        right: -50%;
        animation: bg__line 8s ease-out 1.5s infinite normal forwards;
      }
    }
  }
  .main {
    padding: 40px 0 0 0;
    &__title {
      margin: 0;
    }
    &__logo {
      width: 250px;
      bottom: -20px;
    }
  }
}
@media (max-width: 576px) {
  section,
  header,
  footer {
    padding: 0 calc(50vw - 238px);
  }

  .line {
    &__first {
      width: 274px;
      top: 4%;
      right: -10%;
    }
    &__second {
      width: 306px;
      top: 16%;
      right: -17%;
    }
    &__third {
      width: 231px;
      top: 8%;
      right: -11%;
    }
    &__bg {
      &-first {
        top: -100%;
        width: 231px;
        right: -100%;
        animation: bg__line 12s ease-out 1.5s infinite normal forwards;
      }
      &-second {
        top: -100%;
        width: 231px;
        right: 0%;
        animation: bg__line 11s ease-out 1.5s infinite normal forwards;
      }
      &-third {
        width: 231px;
        top: -100%;
        right: -70%;
        animation: bg__line 11s ease-out 1.5s infinite normal forwards;
      }
      &-forth {
        width: 231px;
        top: -100%;
        right: -50%;
        animation: bg__line 10s ease-out 1.5s infinite normal forwards;
      }
    }
  }
  .main {
    padding: 50px 0 0 0;
    &__icon {
      width: 140px;
    }
    &__title {
      font-size: 110px;
      margin: 0;
    }

    &__text {
      font-size: 15px;
      &.special {
        font-size: 40px;
      }
    }
    &__logo {
      width: 210px;
      bottom: 55px;
    }
    &__button {
      width: 100%;
      padding: 15px 0;
    }
    .wrapper {
      width: 362px;
    }
  }
}
@media (max-width: 480px) {
  section,
  header,
  footer {
    padding: 0 calc(35vw - 105px);
  }
  .line {
    &__first {
      width: 274px;
      top: -32%;
      right: -15%;
    }
    &__second {
      width: 306px;
      top: -21%;
      right: -33%;
    }
    &__third {
      width: 231px;
      top: -30%;
      right: -22%;
    }
    &__bg {
      &-first {
        top: -100%;
        width: 231px;
        right: -100%;
        animation: bg__line 12s ease-out 1.5s infinite normal forwards;
      }
      &-second {
        top: -100%;
        width: 231px;
        right: 0%;
        animation: bg__line 11s ease-out 1.5s infinite normal forwards;
      }
      &-third {
        width: 231px;
        top: -100%;
        right: -70%;
        animation: bg__line 11s ease-out 1.5s infinite normal forwards;
      }
      &-forth {
        width: 231px;
        top: -100%;
        right: -50%;
        animation: bg__line 10s ease-out 1.5s infinite normal forwards;
      }
    }
  }
  .main {
    padding-top: 50px;
    &__icon {
      width: 64px;
    }
    &__logo {
      width: 160px;
      right: 15px;
      bottom: 39px;
    }
    &__title {
      font-size: 88px;
      margin-top: 0;
    }
    &__text {
      font-size: 12px;
      &.special {
        font-size: 32px;
      }
    }
    &__button {
      width: 100%;
      font-size: 16px;
      padding: 10px 0;
    }
    .wrapper {
      justify-content: center;
      width: 290px;
    }
  }
}
</style>
