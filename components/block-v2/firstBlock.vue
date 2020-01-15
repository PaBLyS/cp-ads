<template>
  <section class="firstBlock">
    <img src="/logo-v2.png">
    <div class="firstBlock__content">
      <h2 class="firstBlock__content-label">Построй свою карьеру в IT вместе с The Ad Masters!</h2>
      <p class="firstBlock__content-text">Мы верим в интеллект, страсть и желание учиться новому. Если у вас немного или
        совсем нет опыта, но вы хотите освоить новую профессию — мы с радостью всему научим.
      </p>
    </div>
    <nuxt-link to="/popup-form">
      <button class="firstBlock__button">
        Подать заявку
      </button>
    </nuxt-link>
  </section>
</template>

<script>
    export default {
        name: "firstBlock"
    }
</script>

<style lang="scss" scoped>
  .__layuot {
    font-family: 'Open Sans', sans-serif;
  }

  .firstBlock {
    padding: 150px 30px 80px;
    height: 100vh;
    background: url('/fon-firstBlock-v2.png') no-repeat;
    background-size: cover;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-around;

    &__content {
      color: #fff;
      text-align: center;
      max-width: 1140px;

      &-label {
        font-family: 'Montserrat', sans-serif;
        font-style: normal;
        font-weight: 600;
        font-size: 54px;
        line-height: 66px;
      }

      &-text {
        font-family: 'Open Sans', sans-serif;
        margin: 30px 100px;
        font-style: normal;
        font-weight: 300;
        font-size: 24px;
        line-height: 28px;
      }
    }

    &__button {
      border: 1px solid #39D4EC;
      background: transparent;
      border-radius: 4px;
      padding: 15px 100px;
      color: #fff;
      font-family: 'Open Sans', sans-serif;
      text-transform: uppercase;
      font-style: normal;
      font-weight: bold;
      font-size: 18px;
      line-height: 25px;
      margin: 10px 0;

      &:hover {
        background: linear-gradient(90deg, #35B5FC 0.42%, #39D5EB 100%);
      }
    }
  }

  @media only screen and (min-width: 992px) and (max-width: 1200px) {

  }

  @media only screen and (min-width: 768px) and (max-width: 991px) {

  }

  @media only screen and (min-width: 576px) and (max-width: 767px) {
    .firstBlock {

      &__content {

        &-label {
          font-size: 32px;
          line-height: 50px;
          margin-top: 30px;
        }

        &-text {
          font-weight: 500;
          font-size: 18px;
          line-height: 24px;
          margin: 0;
        }
      }
    }
  }

  @media only screen and (max-width: 575px) {
    .firstBlock {

      img {
        width: 100%;
      }

      &__content {

        &-label {
          font-size: 28px;
          line-height: 35px;
          margin-top: 30px;
        }

        &-text {
          font-weight: 500;
          font-size: 16px;
          line-height: 22px;
          margin: 0;
        }
      }
    }
  }
</style>
