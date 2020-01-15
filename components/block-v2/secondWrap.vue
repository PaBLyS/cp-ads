<template>
  <section class="secondWrap">

    <second-block-v2/>

<!--    <b-container fluid class="thirdBlock">-->
<!--      <b-row class="justify-content-center">-->
<!--        <b-col xl="6" cols="11">-->
<!--          <p class="thirdBlock__text">Даже если вы не найдёте позицию по душе, смело отправляйте заявку. Мы свяжемся с-->
<!--            вами, чтобы обсудить все-->
<!--            возможности.</p>-->
<!--        </b-col>-->
<!--      </b-row>-->
<!--    </b-container>-->

<!--    <vacancies-block-v2/>-->

  </section>
</template>

<script>
    import secondBlockV2 from "./secondBlock";
    import vacanciesBlockV2 from "./vacanсiesBlock";

    export default {
        components: {secondBlockV2, vacanciesBlockV2},
        mounted() {
        },
        name: "secondWrap"
    }
</script>

<style lang="scss" scoped>
  .secondWrap {
    position: relative;
    overflow: hidden;
    background-color: #F3F7FA;
    background-image: url('/net-bg.png');
    background-repeat: no-repeat;
    background-position: center top;
    background-size: 100% auto;

    .thirdBlock {
      background: linear-gradient(90deg, rgba(53, 181, 252, 0.75) 0.42%, rgba(57, 213, 235, 0.75) 100%);
      backdrop-filter: blur(4px);
      padding: 50px 0;

      &__text {
        color: #fff;
        font-family: 'Montserrat', sans-serif;
        font-style: normal;
        font-weight: 600;
        font-size: 36px;
        line-height: 45px;
        text-align: center;
      }
    }
  }

  .fonV2 {
    position: absolute;
    top: 0;
    height: 100%;
    width: 80%;
    z-index: -1;

    canvas {
      height: 100%;
      width: 100%;
    }
  }

  #fon-left {
    left: -50%;
  }

  #fon-right {
    right: 50%;
  }

  @media only screen and (min-width: 992px) and (max-width: 1200px) {
    .secondWrap {
      background-image: none;
    }
  }

  @media only screen and (min-width: 768px) and (max-width: 991px) {
    .secondWrap {
      background-image: none;
    }
  }

  @media only screen and (min-width: 576px) and (max-width: 767px) {
    .secondWrap {
      background-image: none;
    }
  }

  @media only screen and (max-width: 575px) {
    .secondWrap {
      background-image: none;
    }
  }
</style>
