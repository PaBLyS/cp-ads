<template>
  <div class="section">
    <b-container class="section__container">
      <b-row class="section__row align-items-center justify-content-end">
        <b-col lg="3" xl="7">
          <ul class="section__row-list">
            <li>
              INNOVATE
            </li>
            <li>
              OUTPERFORM
            </li>
            <li>
              OVERACHIEVE
            </li>
          </ul>
        </b-col>
      </b-row>
      <b-row class="section__row align-items-end justify-content-around">
        <b-col lg="7" xl="7" class="section__row-item1">
          <div class="section__row-img">
            <img src="/top-block-bg.svg">
          </div>
        </b-col>
        <b-col lg="5" xl="5" class="section__row-item2">
          <p class="section__row-content">The world is changing fast, and we make sure we stay ahead of those changes.
            The Ad Masters is an R&D
            provider founded in Chicago in 2019 and is focused on developing online sales and marketing solutions for
            the latest eCommerce trends.</p>
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


  .section {
    padding: {
      top: 100px;
    };

    &__container {
      padding-bottom: 20px;
    }


    &__row {
      margin-bottom: 30px;
      position: relative;

      &-img {
        position: absolute;
        bottom: -140px;
        left: -20px;
      }

      &-line-text {
        font-family: 'Roboto', sans-serif;
        text-transform: uppercase;
        font-style: normal;
        font-weight: 900;
        font-size: 150px;
        line-height: 176px;
      }

      &-gradient-text img {
        width: 100%;
        object-fit: contain;
      }

      &-list {
        display: flex;
        margin: 0;
        padding: 0;
        color: #fff;

        li {
          list-style: none;
          display: flex;
          align-items: center;
          font-weight: 300;
          font-size: 20px;
          letter-spacing: 0.06em;

          &:before {
            content: '';
            display: block;
            height: 22px;
            width: 22px;
            border-radius: 100%;
            background-color: #5D2CFF;
            margin: 0 15px 0 25px;
          }
        }
      }

      &-content {
        font-size: 19px;
        line-height: 30px;
        color: #fff;
      }
    }
  }

  @media only screen and (min-width: 992px) and (max-width: 1199px) {
    .section {

      &__row {

        &-line-text {
          font-size: 130px;
        }

        &-list {
          display: block;

          li {
            padding-bottom: 10px;

          }
        }
      }
    }
  }

  @media only screen and (min-width: 768px) and (max-width: 991px) {
    .section {

      &__row {

        &-line-text {
          font-size: 130px;
        }

        &-list {


          li {
            padding-bottom: 10px;

          }
        }
      }
    }
  }

  @media only screen and (min-width: 577px) and (max-width: 767px) {

  }

  @media only screen and (max-width: 576px) {

  }
</style>
