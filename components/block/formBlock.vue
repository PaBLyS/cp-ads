<template>
  <section class="wrap">
    <b-container>
      <b-row class="justify-content-end">
        <b-col cols="3" class="wrap__img">
          <img src="/form-text.png">
        </b-col>
        <b-col cols="9" class="wrap__form-col">
          <custom-from/>
        </b-col>
      </b-row>
    </b-container>
  </section>
</template>

<script>
    import customFrom from "../elements/customFrom";

    export default {
        name: "formBlock",
        components: {customFrom}
    }
</script>

<style lang="scss" scoped>
  .wrap {
    padding: 60px 0;
    background-image: url('/form-circle.png');
    background-repeat: no-repeat;
    background-position: 20% 75%;

    &__img {
      position: relative;

      img{
        position: absolute;
        top: 27%;
        z-index: 100;
      }
    }

    &__form-col {
      transform: translateX(100px);
    }
  }
</style>
