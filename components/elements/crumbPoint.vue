<template>
  <div class="crumbPoint">
    <div class="crumbPoint__img">
      <img :src="imgUrl">
    </div>
    <p class="crumbPoint__content">{{content}}</p>
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
  .crumbPoint {
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
