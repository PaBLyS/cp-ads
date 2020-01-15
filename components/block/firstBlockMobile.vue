<template>
  <section class="firstBlockMobile">
    <div class="img__wrap">
      <img src="/top-mobile-bg.png" class="img">
    </div>
    <p class="firstBlockMobile__item item-1">INNOVATE</p>
    <p class="firstBlockMobile__item item-2">OUTPERFORM</p>
    <p class="firstBlockMobile__item item-3">OVERACHIEVE</p>
    <div class="firstBlockMobile__circle">
      <div class="firstBlockMobile__circle-elem"></div>
      <div class="firstBlockMobile__circle-elem"></div>
      <div class="firstBlockMobile__circle-elem"></div>
    </div>
    <p class="firstBlockMobile__content">
      The world is changing fast, and we make sure we stay ahead of those changes. The Ad Masters is an R&D provider
      founded in Chicago in 2019 and is focused on developing online sales and marketing solutions for the latest
      eCommerce trends.
    </p>
  </section>
</template>

<script>
    export default {
        name: "firstBlockMobile"
    }
</script>

<style lang="scss" scoped>
  .img {
    width: 100%;
    object-fit: cover;

    &__wrap {
      width: 100%;
      margin-bottom: 35px;
    }
  }

  .firstBlockMobile {

    &__item {
      font-family: 'Comfortaa', sans-serif;
      font-style: normal;
      font-weight: 300;
      font-size: 24px;
      line-height: 60px;
      margin: 0 25px;

      &.item-1 {
        color: #787878;
      }

      &.item-2 {
        color: #00FFA5;
      }

      &.item-3 {
        color: #663BE0;
      }
    }

    &__circle {
      display: flex;
      justify-content: space-around;
      margin: 35px 25px;

      &-elem {
        height: 25px;
        width: 25px;
        border-radius: 100%;
        background-color: #00FFA5;
      }
    }

    &__content {
      font-family: 'Comfortaa', sans-serif;
      font-style: normal;
      font-weight: normal;
      font-size: 19px;
      line-height: 30px;
      color: #FFFFFF;
      margin: 0 25px 50px;
    }
  }
</style>
