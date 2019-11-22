<template>
  <div class="form-wrap">
    <form action="" class="form">
      <p class="form__label">Please verify or enter your personal information below: </p>
      <div class="form__row">
        <input :type="input[0].type"
               class="form__row-input"
               :placeholder="input[0].placeholder"
               v-model="input[0].value">
      </div>
      <div class="form__row">
        <input :type="input[1].type"
               class="form__row-input"
               :placeholder="input[1].placeholder"
               v-model="input[1].value">
        <input :type="input[2].type"
               class="form__row-input"
               :placeholder="input[2].placeholder"
               v-model="input[2].value">
      </div>
      <p class="form__row-descr">Choose your position:</p>
      <div class="form__row">
        <select name="" id="" class="form__row-input">
          <option selected disabled>Select one</option>
          <option value="node">Node</option>
          <option value="react">React</option>
          <option value="vue">Vue</option>
        </select>
      </div>
      <div class="form__row">
        <span class="form__row-cv">Upload your CV</span>
        <label for="uploadFile">
          <div class="form__row-btn-upload">Browse...</div>
          <input type="file" id="uploadFile" style="display: none;" :value="null">
        </label>
      </div>
      <div :class="['submit', formValid ? 'active' : null]">
        <div class="input" @click="uploadForm">
          Submit
          <span></span>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
    import is from 'is_js';

    export default {
        name: "customFrom",
        data() {
            return {
                input: [
                    {
                        type: 'text',
                        placeholder: 'Please enter your full name*',
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
                        placeholder: 'Phone number*',
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

<style lang="scss">
  .form {

    &-wrap {
      padding: 65px 115px;
      background: #3F3169;
      box-shadow: 7px 30px 50px rgba(100, 47, 225, 0.16);
      border-radius: 25px;
    }

    &__label {
      color: #00FFA5;
      font-family: 'Comfortaa', sans-serif;
      font-style: normal;
      font-weight: bold;
      font-size: 18px;
      line-height: 36px;
    }

    &__row {
      display: flex;
      justify-content: space-between;
      align-items: center;
      width: 100%;
      margin-bottom: 20px;

      &-descr {
        color: #fff;
        font-family: 'Comfortaa', sans-serif;
        font-style: normal;
        font-weight: normal;
        font-size: 14px;
        line-height: 23px;
      }

      &-cv {
        font-size: 18px;
        line-height: 23px;
        color: rgba(255, 255, 255, 0.9);
        font-family: 'Comfortaa', sans-serif;
        font-style: normal;
        font-weight: normal;
      }

      &-btn-upload {
        padding: 17px 65px;
        font-weight: bold;
        font-size: 20px;
        line-height: 22px;
        color: #6D5ADE;
        cursor: url('/coursor-hover.png') 4 4, pointer;

        &:hover {
          color: #554daa;
          text-decoration: underline;
        }
      }

      &-input {
        border-radius: 10px;
        height: 80px;
        width: 100%;
        font-size: 18px;
        line-height: 23px;
        border: none;
        padding: 0 30px;
        appearance: none;
        cursor: url('/coursor-hover.png') 4 4, pointer;


        &:nth-child(2) {
          margin-left: 15px;
        }

        &::placeholder {
          color: rgba(0, 0, 0, 0.4);
        }

        &:active, &:focus {
          outline: none;
        }
      }
    }

    .submit {
      cursor: url('/coursor.png') 4 4, auto;

      &.active {
        cursor: url('/coursor-hover.png') 4 4, pointer;
        .input {
          $border-active: 1px solid #0BFFB6;
          color: #0BFFB6;

          &:before {
            border-top: $border-active;
            border-left: $border-active;
          }

          &:after {
            border-top: $border-active;
            border-right: $border-active;
          }

          span:before {
            border-bottom: $border-active;
            border-left: $border-active;
          }

          span:after {
            border-bottom: $border-active;
            border-right: $border-active;
          }

          &:hover:before,
          &:hover:after,
          &:hover span:before,
          &:hover span:after {
            width: 49%;
            height: 45%;
          }
        }
      }

      .input {
        $border: 1px solid rgb(104, 103, 110);

        position: relative;
        font-family: 'Comfortaa', sans-serif;
        font-style: normal;
        font-weight: bold;
        font-size: 20px;
        line-height: 22px;
        text-align: center;
        color: rgb(104, 103, 110);
        padding: 15px 80px;
        transition: color .3s;
        text-decoration: none;

        &:before,
        &:after,
        span:before,
        span:after {
          content: '';
          position: absolute;
          width: 10px;
          height: 10px;
          background: transparent;
          transition: 1s;
        }

        &:before {
          top: -2px;
          left: -2px;
          border-top: $border;
          border-left: $border;
        }

        &:after {
          top: -2px;
          right: -2px;
          border-top: $border;
          border-right: $border;
        }

        span:before {
          bottom: -2px;
          left: -2px;
          border-bottom: $border;
          border-left: $border;
        }

        span:after {
          bottom: -2px;
          right: -2px;
          border-bottom: $border;
          border-right: $border;
        }
      }
    }
  }
</style>
