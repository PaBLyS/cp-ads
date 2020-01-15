<template>
  <section class="formBlock-all">
    <b-container class="formBlock">
      <b-row>
        <b-col lg="5" cols="12" class="formBlock__text">
          <div class="formBlock__text-all">
            <p class="formBlock__text-top">enter</p><br>
            <p class="formBlock__text-center">Your</p><br>
            <p class="formBlock__text-bottom">information</p>
          </div>
          <img src="/form-circle.png" class="formBlock__text-img">
        </b-col>
        <b-col lg="7" cols="12">
          <custom-from/>
        </b-col>
      </b-row>
      <b-row class="justify-content-end">
        <b-col lg="7" cols="12">
          <social-icon/>
        </b-col>
      </b-row>
    </b-container>
  </section>
</template>

<script>
    import customFrom from "../elements/customFrom";
    import socialIcon from "../elements/socialIcon";

    export default {
        name: "formBlock",
        components: {customFrom, socialIcon}
    }
</script>

<style lang="scss" scoped>
  .formBlock {
    margin: {
      bottom: 40px;
    };

    &-all {
      width: 100%;
      overflow: hidden;
      background: #221B37;
    }

    &__text {
      padding-top: 50px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      margin-bottom: 30px;

      p {
        margin: 0;
      }

      &-img {
        height: 110%;
        position: absolute;
        top: 0;
        z-index: -1;
      }

      &-all {
        font-family: 'Roboto', sans-serif;
        font-style: normal;
        font-weight: 900;
        text-transform: uppercase;
        color: #00FFA5;
      }

      &-top {
        font-size: 144px;
        line-height: 140px;
        -webkit-text-fill-color: transparent;
        -webkit-text-stroke: 2px #00FFA5;
      }

      &-center {
        font-size: 144px;
        line-height: 130px;
      }

      &-bottom {
        font-size: 64px;
        line-height: 60px;
        -webkit-text-fill-color: transparent;
        -webkit-text-stroke: 2px #00FFA5;
      }
    }
  }

  @media only screen and (min-width: 768px) and (max-width: 991px) {
    .formBlock {

      &__text {
        text-align: center;

        &-img {
          height: 200%;
          top: 0;
          right: -100px;
        }

        &-top {
          font-size: 128px;
          line-height: 120px;
        }

        &-center {
          font-size: 112px;
          line-height: 120px;
        }

        &-bottom {
          font-size: 64px;
          line-height: 75px;
        }
      }
    }
  }

  @media only screen and (min-width: 576px) and (max-width: 767px) {
    .formBlock {

      &__text {
        text-align: center;

        &-img {
          height: 150%;
          top: 0;
          right: -100px;
        }

        &-top {
          font-size: 128px;
          line-height: 120px;
        }

        &-center {
          font-size: 112px;
          line-height: 120px;
        }

        &-bottom {
          font-size: 64px;
          line-height: 75px;
        }
      }
    }
  }

  @media only screen and (max-width: 575px) {
    .formBlock {

      &__text {
        text-align: center;

        &-img {
          height: 200%;
          left: 0;
        }

        &-top {
          font-size: 60px;
          line-height: 70px;
        }

        &-center {
          font-size: 80px;
          line-height: 70px;
        }

        &-bottom {
          font-size: 40px;
          line-height: 45px;
        }
      }
    }
  }
</style>
