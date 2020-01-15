<template>
  <section class="diagramBlock__wrap">
    <b-container class="diagramBlock">
      <b-row>
        <b-col class="diagramBlock__label">
          <p>Our <span class="diagramBlock__label-sub">Mission</span></p>
        </b-col>
      </b-row>
      <b-row>
        <b-col lg="6" class="diagramBlock__content-wrap">
          <p class="diagramBlock__content">
            The Ad Masters technology solutions empower businesses to spread their message and products to change lives.
          </p>
          <img class="diagramBlock__diagram diagramBlock__diagram-second-mob" src="/diagram-2-mob.png">
          <img class="diagramBlock__diagram diagramBlock__diagram-first" src="/diagram-1.png">
        </b-col>
        <b-col lg="6">
          <img class="diagramBlock__diagram diagramBlock__diagram-second" src="/diagram-2.png">
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
  .diagramBlock {
    padding: 100px 0 30px;

    &__wrap {
      background: #221B37;
    }

    &__label {
      color: white;
      font-family: 'Roboto', sans-serif;
      font-style: normal;
      font-weight: 900;
      font-size: 106px;
      line-height: 124px;
      -webkit-text-fill-color: transparent;
      -webkit-text-stroke: 2px #7C49F4;
      margin-bottom: 50px;

      &-sub {
        background: url("/elips.png") no-repeat center/contain;
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        -webkit-text-stroke: 2px #7C49F4;
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
      object-fit: contain;

      &-second {
        &-mob {
          display: none;
        }
      }
    }
  }

  @media only screen and (min-width: 576px) and (max-width: 767px) {
    .diagramBlock {
      padding: 15px;

      &__diagram-second {
        display: none;

        &-mob {
          display: block;
        }
      }
    }

    .diagramBlock__label {
      font-size: 80px;
      line-height: 80px;
      margin: {
        top: 20px;
        bottom: 0;
        left: 0;
        right: 0;
      };
    }
  }

  @media only screen and (max-width: 575px) {
    .diagramBlock {
      padding: 0 15px 30px;

      &__label {
        font-size: 80px;
        line-height: 80px;
        margin: {
          top: 20px;
          bottom: 0;
          left: 0;
          right: 0;
        };
      }

      &__content {
        font-weight: 300;
        font-size: 16px;
      }

      &__diagram-second {
        display: none;

        &-mob {
          display: block;
        }
      }
    }
  }
</style>
