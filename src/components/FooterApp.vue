<template>
  <footer class="footer">
    <div class="footer__box">
      <div class="wrapper footer__wallets wallets">
        <img
          v-for="(item, index) of wallets"
          :key="index"
          :src="require(`@/assets/img/wallets/${item}`)"
          alt="wallet"
        />
      </div>
      <div class="wrapper footer__wallets coins">
        <img
          v-for="(item, index) of coins"
          :key="index"
          :src="require(`@/assets/img/coins/${item}`)"
          alt="coin"
        />
      </div>
    </div>
    <p class="footer__licence">© 2023 Dragon Money. All rights reserved</p>
  </footer>
</template>

<script setup>
const wallets = ['plast.png', 'visa.png', 'p2p.png', 'fk.png', 'ym.png'];
const coins = ['bit.png', 'lite.png', 'eth.png'];
</script>

<style lang="scss" scoped>
.footer {
  background: linear-gradient(180deg, rgba(24, 26, 37, 0) 0%, #060818 36.46%);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 60px;
  padding: 150px 0 15px;

  &__box {
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 24px;
  }
  &__licence {
    color: #fff;
    font-size: 14px;
    font-weight: 400;
  }
  .wallets {
    display: flex;
    align-items: flex-end;
    gap: 25px;
  }
  .coins {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 31px;
  }
}
@media (max-width: 576px) {
  .footer{
    padding: 50px 0 15px;
    gap: 40px;
    .wallets {
      gap: 10px;
      justify-content: center;
      img {
        &:nth-child(1) {
          width: 75px;
        }
        &:nth-child(2) {
          width: 75px;
        }
        &:nth-child(3) {
          width: 75px;
        }
        &:nth-child(4) {
          width: 75px;
        }
        &:nth-child(5) {
          width: 75px;
        }
      }
    }
    .coins {
      gap: 12px;
      img {
        &:nth-child(1) {
          width: 70px;
        }
        &:nth-child(2) {
          width: 70px;
        }
        &:nth-child(3) {
          width: 90px;
        }
      }
    }
  }
}
@media (max-width: 480px) {
  .footer {
    gap: 33px;
    padding: 38px 0 7px;
    &__box{
      gap: 8px;
    }
    .wallets {
      gap: 10px;
      justify-content: center;
      img {
        &:nth-child(1) {
          width: 36px;
        }
        &:nth-child(2) {
          width: 41px;
        }
        &:nth-child(3) {
          width: 44px;
        }
        &:nth-child(4) {
          width: 45px;
        }
        &:nth-child(5) {
          width: 49px;
        }
      }
    }
    .coins {
      gap: 12px;
      img {
        &:nth-child(1) {
          width: 34px;
        }
        &:nth-child(2) {
          width: 31px;
        }
        &:nth-child(3) {
          width: 41px;
        }
      }
    }
    &__licence{
      font-size: 7px;
    }
  }
}
</style>
