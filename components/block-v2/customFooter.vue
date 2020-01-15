<template>
  <section class="customFooter">
    <b-container>
      <b-row align-v="center" class="justify-content-between">
        <b-col md="3" cols="12" class="customFooter__sub">
          <img src="/logo-footer.png">
          <p class="customFooter__sublabel">© 2019 The Ad Masters, All Rights Reserved.</p>
        </b-col>
        <b-col md="5" cols="12">
          <nuxt-link to="/popup-form">
            <div class="customFooter__button">
              Подать заявку сейчас
            </div>
          </nuxt-link>
        </b-col>
        <b-col md="3" cols="12" class="customFooter__link-wrap">
<!--         <div class="customFooter__link">-->
<!--           <a href="/">Контакты</a>-->
<!--           <a href="/">Офисы</a>-->
<!--         </div>-->
          <social-icon-v2/>
        </b-col>
      </b-row>
    </b-container>
  </section>
</template>

<script>
    import socialIconV2 from "../elements/socialIconV2";

    export default {
        name: "customFooter",
        components: {socialIconV2}
    }
</script>

<style lang="scss" scoped>
  .customFooter {
    background: linear-gradient(90deg, #35B5FC 0.42%, #39D5EB 100%);
    padding: 15px 0;

    &__sub {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;

    }

    &__sublabel {
      font-family: 'Helvetica LT', sans-serif;
      font-style: normal;
      font-weight: normal;
      font-size: 11px;
      line-height: 13px;
      color: #FFFFFF;
      margin-top: 10px;
      text-align: center;
    }

    &__button {
      font-family: 'Open Sans', sans-serif;
      font-style: normal;
      font-weight: normal;
      font-size: 24px;
      line-height: 33px;
      text-align: center;
      color: #FFFFFF;

      &:hover {
        text-decoration: underline;
        cursor: pointer;
      }
    }

    &__link {

      a {
        display: inline-block;
        margin: {
          right: 50px;
          bottom: 10px;
        };
        font-family: 'Open Sans', sans-serif;
        font-style: normal;
        font-weight: normal;
        font-size: 14px;
        line-height: 19px;
        color: #FFFFFF;
      }
    }
  }

  @media only screen and (min-width: 576px) and (max-width: 767px) {
    .customFooter {
      .row {
        flex-direction: column;
      }

      &__button {
        margin: 20px 0;
      }
    }
  }

  @media only screen and (max-width: 575px) {
    .customFooter {
      .row {
        flex-direction: column;
      }

      &__button {
        margin: 20px 0;
      }
    }
  }
</style>
