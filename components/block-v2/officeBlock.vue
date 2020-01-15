<template>
  <div class="offiseBlock">
    <h2 class="offiseBlock__label">Наши преимущества</h2>
    <b-container class="offiseBlock__wrap">
      <div v-for="elem in element"
           class="offiseBlock__wrap-elem">
        <img :src="elem.urlImg" class="offiseBlock__wrap-elem-img">
        <div class="offiseBlock__wrap-elem-text-wrap">
          <p class="offiseBlock__wrap-elem-text">{{elem.text}}</p>
        </div>
      </div>
    </b-container>
  </div>
</template>

<script>
    export default {
        name: "offiseBlock",
        data() {
            return {
                element: [
                    {
                        text: 'Работа в быстрорастущей Аммериканской компании ',
                        urlImg: '/offiseImgPoint/1.png'
                    },
                    {
                        text: 'Офис в центре Киева',
                        urlImg: '/offiseImgPoint/2.png'
                    },
                    {
                        text: 'Молодой и дружный коллектив',
                        urlImg: '/offiseImgPoint/3.png'
                    },
                    {
                        text: 'Все для комфортной роботы',
                        urlImg: '/offiseImgPoint/4.png'
                    },
                    {
                        text: 'Удобный график',
                        urlImg: '/offiseImgPoint/5.png'
                    }
                ]
            }
        }
    }
</script>

<style lang="scss" scoped>
  .offiseBlock {
    background-image: url("/offiseImgPoint/fon.png");
    background-repeat: no-repeat;
    background-size: cover;
    text-align: center;
    padding-bottom: 100px;

    &__label {
      font-family: 'Montserrat', sans-serif;
      font-style: normal;
      font-weight: 600;
      font-size: 48px;
      line-height: 59px;
      color: #FFFFFF;
      padding: 40px 0;
    }

    &__wrap {
      display: flex;
      justify-content: space-around;
      flex-wrap: wrap;

      &-elem {
        background: rgba(0, 0, 0, 0.85);
        border-radius: 5px;
        padding: 25px 15px;
        width: 175px;
        min-width: 175px;
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: center;
        margin: 5px;


        &-img {
          margin-bottom: 15px;
        }

        &-text {
          margin: 0;
          font-family: 'Open Sans', sans-serif;
          font-style: normal;
          font-weight: normal;
          font-size: 18px;
          line-height: 23px;
          color: #FFFFFF;

          &-wrap {
            display: flex;
            align-items: center;
            height: 100%;
          }
        }
      }
    }
  }

  @media only screen and (min-width: 992px) and (max-width: 1200px) {

  }

  @media only screen and (min-width: 768px) and (max-width: 991px) {

  }

  @media only screen and (min-width: 576px) and (max-width: 767px) {
    .offiseBlock {

      &__wrap {
        flex-direction: column;
        align-items: center;
      }
    }
  }

  @media only screen and (max-width: 575px) {
    .offiseBlock {

      &__label {
        font-size: 28px;
      }

      &__wrap {
        flex-direction: column;
        align-items: center;

        &-elem-text {
          font-size: 16px;
        }
      }
    }
  }
</style>
