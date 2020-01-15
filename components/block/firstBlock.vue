<template>
  <div>
    <b-container class="firstBlock">
      <b-row class="justify-content-end" align-v="center">
        <b-col lg="7" cols="12" class="firstBlock__img-wrap">
          <img src="/top-block-bg.png" class="firstBlock__img">
        </b-col>
        <b-col lg="5" cols="12">
          <p class="firstBlock__content">The world is changing fast, and we make sure we stay ahead of those changes.
            The Ad Masters is an R&D provider founded in Chicago in 2019 and is focused on developing online sales and
            marketing solutions for the latest eCommerce trends.</p>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
    export default {
        name: "firstBlock"
    }
</script>

<style lang="scss" scoped>
  .firstBlock {

    &__img {
      width: 100%;
      object-fit: contain;

      &-wrap {
        width: 100%;
      }
    }

    &__content {
      color: #fff;
      font-family: 'Comfortaa', sans-serif;
      font-style: normal;
      font-weight: normal;
      font-size: 19px;
      line-height: 30px;
    }
  }
</style>
