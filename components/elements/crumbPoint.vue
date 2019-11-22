<template>
  <div class="wrap">
    <div class="wrap__img">
      <img :src="imgUrl">
    </div>
    <p class="wrap__content">{{content}}</p>
  </div>
</template>

<script>
    export default {
        name: "crumbPoint",
        props: {
            imgUrl: String,
            content: String
        }
    }
</script>

<style lang="scss" scoped>
  .wrap {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 75px 0 50px;
    border: {
      top: 1px solid #fff;
    };

    &:before {
      content: '';
      height: 35px;
      width: 2px;
      background-color: #fff;
      position: absolute;
      top: 0;
    }

    &__img {
      margin-bottom: 30px;
    }

    &__content {
      color: #fff;
      font-weight: 300;
      font-size: 24px;
      line-height: 27px;
    }
  }
</style>
