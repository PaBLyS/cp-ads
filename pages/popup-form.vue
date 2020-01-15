<template>
  <section class="popup">
    <div class="popup__header">
      <img src="/logo-footer.png">
      <nuxt-link to="/">
        <img src="/close.png">
      </nuxt-link>
    </div>
    <div class="popup__form-wrap">
      <p class="popup__form__label">
        Даже если вы не нашли позицию по душе, смело отправляйте заявку. Мы свяжемся с вами, чтобы обсудить все
        возможности.
      </p>
      <form action="" class="popup__form">
        <div class="popup__form__row">
          <input :type="input[0].type"
                 class="popup__form__row-input"
                 :placeholder="input[0].placeholder"
                 v-model="input[0].value">
        </div>
        <div class="popup__form__row">
          <input :type="input[1].type"
                 class="popup__form__row-input"
                 :placeholder="input[1].placeholder"
                 v-model="input[1].value">
        </div>
        <div class="popup__form__row">
          <input :type="input[2].type"
                 class="popup__form__row-input"
                 :placeholder="input[2].placeholder"
                 v-model="input[2].value">
        </div>
        <div class="popup__form__row">
          <select name="" id="" class="popup__form__row-input">
            <option selected disabled>Желаемая должность:</option>
            <option value="node">Node</option>
            <option value="react">React</option>
            <option value="vue">Vue</option>
          </select>
        </div>
        <div class="popup__form__row">
          <span class="popup__form__row-cv">Резюме (Word, PDF)</span>
          <label for="uploadFile">
            <div class="popup__form__row-upload">Загрузить...</div>
            <input type="file" id="uploadFile" style="display: none;" :value="null">
          </label>
        </div>
        <div class="popup__form__row">
          <div :class="['submit', formValid ? 'active' : null]">
            <div class="input" @click="uploadForm">
              ОТПРАВИТЬ
            </div>
          </div>
        </div>
      </form>
    </div>
  </section>
</template>

<script>
    import is from 'is_js';

    export default {
        name: "popup-form",
        data() {
            return {
                input: [
                    {
                        type: 'text',
                        placeholder: 'Имя Фамилия*',
                        touch: false,
                        value: '',
                        error: 'Invalid full name'
                    },
                    {
                        type: 'email',
                        placeholder: 'Email*',
                        touch: false,
                        value: '',
                        error: 'Invalid Email'
                    },
                    {
                        type: 'text',
                        placeholder: 'Номер телефона*',
                        touch: false,
                        value: '',
                        error: 'Number start on 0'
                    }
                ]
            }
        },
        computed: {
            valid() {
                return [
                    this.input[0].value.length > 5,
                    is.email(this.input[1].value),
                    /^[+]*[(]{0,1}[0-9]{1,4}[)]{0,1}[-\s\./0-9]*$/.test(this.input[2].value) && this.input[2].value.length > 9 && this.input[2].value.length < 13
                ]
            },
            formValid() {
                return this.valid[0] && this.valid[1] && this.valid[2]
            }
        },
        methods: {
            uploadForm(e) {
                if (this.formValid) this.$router.push('/thank-you');
            }
        }
    }
</script>

<style lang="scss" scoped>
  .popup {
    height: 100vh;
    width: 100vw;
    background-image: url('/popup-fon.png');
    background-size: cover;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-around;

    &__header {
      width: 1140px;
      display: flex;
      justify-content: space-between;
      align-items: center;

      img[src="/close.png"] {
        cursor: pointer;
      }
    }

    &__form {
      width: 360px;

      &-wrap {
        display: flex;
        flex-direction: column;
        align-items: center;
      }

      &__label {
        width: 640px;
        text-align: center;
        font-family: 'Helvetica LT', sans-serif;
        font-style: normal;
        font-weight: normal;
        font-size: 18px;
        line-height: 25px;
        letter-spacing: 0.02em;
        color: #FFFFFF;
      }

      &__row {
        width: 100%;
        display: flex;
        justify-content: space-between;
        margin: 25px 0;

        &-input {
          width: 100%;
          background: #FFFFFF;
          border: none;
          border-radius: 3px;
          padding: 15px;
        }

        &-cv {
          color: #fff;
          font-family: 'Helvetica LT', sans-serif;
          font-style: normal;
          font-weight: normal;
          font-size: 14px;
          line-height: 16px;
        }

        &-upload {
          color: #fff;
          font-family: 'Helvetica LT', sans-serif;
          font-style: normal;
          font-weight: bold;
          font-size: 14px;
          line-height: 17px;
        }

        .submit {
          padding: 15px 0;
          width: 100%;
          border: 1px solid #a0a1b3;
          border-radius: 4px;
          transition: all .3s;

          &.active {
            cursor: pointer;
            border: 1px solid #39D4EC;

            &:hover {
              background: linear-gradient(90deg, #35B5FC 0.42%, #39D5EB 100%);
            }
          }
        }

        .input {
          width: auto;
          text-align: center;
          font-family: 'Helvetica LT', sans-serif;
          font-style: normal;
          font-weight: bold;
          font-size: 16px;
          line-height: 20px;
          color: #FFFFFF;
        }


      }
    }
  }
</style>
