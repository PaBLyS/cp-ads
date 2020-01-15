<template>
  <div class="aboutUs">
    <b-container class="aboutUs__content">
      <b-row class="justify-content-center">
        <b-col cols="10">
          <h2 class="aboutUs__content-label">О компании</h2>
          <p class="aboutUs__content-text">The Ad Masters разрабатывает передовое программное обеспечение для
            онлайн-продаж и маркетинга,
            предназначенное для предпринимателей и владельцев бизнеса, которые хотят продавать свои услуги и продукты в
            Интернете. Технологические решения The Ad Masters позволяют компаниям распространять свои идеи и продукты
            максимально эффективными методами. Мы растем, собирая умных и талантливых людей вместе. Стань частью нашей
            команды уже сейчас.</p>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
    export default {
        name: "aboutUs"
    }
</script>

<style lang="scss" scoped>
  .aboutUs {
    padding: 50px 0;
    background-color: #F3F7FA;
    background-image: url('/net-bottom.png');
    background-repeat: no-repeat;
    background-size: cover;

    &__content {

      &-label {
        font-family: 'Montserrat', sans-serif;
        font-style: normal;
        font-weight: 600;
        font-size: 48px;
        line-height: 59px;
        color: #333333;
        margin-bottom: 30px;
      }

      &-text {
        font-family: 'Open Sans', sans-serif;
        font-style: normal;
        font-weight: normal;
        font-size: 18px;
        line-height: 25px;
        color: #333333;
      }
    }
  }

  @media only screen and (min-width: 992px) and (max-width: 1200px) {

  }

  @media only screen and (min-width: 768px) and (max-width: 991px) {

  }

  @media only screen and (min-width: 576px) and (max-width: 767px) {

  }

  @media only screen and (max-width: 575px) {
    .aboutUs {
      &__content {

        &-label {
          font-size: 32px;
        }

        &-text {
          font-size: 16px;
        }
      }
    }
  }
</style>
