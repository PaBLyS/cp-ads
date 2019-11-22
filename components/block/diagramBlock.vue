<template>
  <section>
    <b-container class="wrap">
      <b-row>
        <b-col class="wrap__label">
          <p>Our <span class="wrap__label-sub">Mission</span></p>
        </b-col>
      </b-row>
      <b-row>
        <b-col lg="6" class="wrap__content-wrap">
          <p class="wrap__content">
            The Ad Masters technology solutions empower businesses to spread their message and products to change lives.
          </p>
          <img class="wrap__diagram wrap__diagram-first" src="/diagram-1.png">
        </b-col>
        <b-col lg="6">
          <img class="wrap__diagram wrap__diagram-second" src="/diagram-2.png">
        </b-col>
      </b-row>
    </b-container>
  </section>
</template>

<script>
    export default {
        name: "diagramBlock"
    }
</script>

<style lang="scss" scoped>
  .wrap {
    padding: 100px 0 30px;

    &__label {
      color: white;
      font-family: 'Roboto', sans-serif;
      font-style: normal;
      font-weight: 900;
      font-size: 106px;
      line-height: 124px;
      -webkit-text-fill-color: transparent;
      -webkit-text-stroke: 1px #7C49F4;
      margin-bottom: 50px;

      &-sub {
        background: url("/elips.png") no-repeat center/contain;
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        -webkit-text-stroke: 1px #7C49F4;
      }
    }

    &__content {
      color: #fff;
      font-family: 'Comfortaa', sans-serif;
      font-style: normal;
      font-weight: 300;
      font-size: 24px;

      &-wrap {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
      }
    }

    &__diagram {
      width: 100%;

      &-first {

      }

      &-second {
      }
    }
  }
</style>
