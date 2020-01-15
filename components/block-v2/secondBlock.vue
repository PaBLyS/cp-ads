<template>
  <b-container class="secondBlock">
    <b-row>
      <b-col cols="12" class="secondBlock__label">
        Всего 4 шага, к работе своей мечты!
      </b-col>
    </b-row>
    <b-row class="justify-content-center">
      <b-col v-for="elem in element"
             :style="`background-image: url('/number/${elem.id}.png')`"
             class="secondBlock__wrap"
             lg="3" md="6" cols="12"
             :key="elem.id">
        <h3 class="secondBlock__wrap-label">{{elem.label}}</h3>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
    export default {
        name: "secondBlock",
        data() {
            return {
                element: [
                    {
                        id: 1,
                        label: 'Заполни форму'
                    },
                    {
                        id: 2,
                        label: 'Пройди тест'
                    },
                    {
                        id: 3,
                        label: 'Прийди на собеседовние'
                    },
                    {
                        id: 4,
                        label: 'Получи работу'
                    }
                ]
            }
        }
    }
</script>

<style lang="scss" scoped>
  .secondBlock {
    padding-bottom: 80px;

    &__label {
      font-family: 'Montserrat', sans-serif;
      font-style: normal;
      font-weight: 600;
      font-size: 48px;
      line-height: 59px;
      text-align: center;
      margin: 80px 0;
    }

    &__wrap {
      min-height: 160px;
      margin-bottom: 30px;
      background-size: contain;
      background-position: center;
      background-repeat: no-repeat;
      display: flex;
      align-items: center;
      justify-content: center;

      &-label {
        font-family: 'Montserrat', sans-serif;
        font-style: normal;
        font-weight: 600;
        font-size: 24px;
        line-height: 29px;
        text-align: center;
      }
    }
  }

  @media only screen and (min-width: 992px) and (max-width: 1200px) {

  }

  @media only screen and (min-width: 768px) and (max-width: 991px) {

  }

  @media only screen and (min-width: 576px) and (max-width: 767px) {
    .secondBlock {

      &__wrap {
        min-height: 120px;
        margin-bottom: 40px;

        &-label {
          font-size: 20px;
        }
      }

      &__label {
        font-size: 38px;
        line-height: 45px;
      }
    }
  }

  @media only screen and (max-width: 575px) {
    .secondBlock {

      &__wrap {
        min-height: 120px;
        margin-bottom: 40px;

        &-label {
          font-size: 20px;
        }
      }

      &__label {
        font-size: 28px;
        line-height: 45px;
      }
    }
  }
</style>
