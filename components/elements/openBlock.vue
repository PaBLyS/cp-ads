<template>
  <div class="openBlock">
    <div :class="classLabel" @click="changeOpen(index)">
      <div class="openBlock__label-left">
        <span :class="classNum">{{index + 1}}</span>
        <p class="openBlock__label-content">{{label}}</p>
      </div>
      <div class="openBlock__label-arrow">
        <svg x="0px" y="0px"
             viewBox="0 0 41.999 41.999" xml:space="preserve">
          <path d="M36.068,20.176l-29-20C6.761-0.035,6.363-0.057,6.035,0.114C5.706,0.287,5.5,0.627,5.5,0.999v40
            c0,0.372,0.206,0.713,0.535,0.886c0.146,0.076,0.306,0.114,0.465,0.114c0.199,0,0.397-0.06,0.568-0.177l29-20
            c0.271-0.187,0.432-0.494,0.432-0.823S36.338,20.363,36.068,20.176z"></path>
        </svg>
      </div>
    </div>
    <div :class="classDescription">
      <p class="openBlock__description-text">{{content}}</p>
      <button class="openBlock__description-button">Read more</button>
    </div>
  </div>
</template>

<script>
    export default {
        name: "openBlock",
        props: {
            index: Number,
            label: String,
            content: String,
            status: Boolean,
            changeOpen: Function
        },
        data() {
            return {

            }
        },
        computed: {
            classDescription() {
                return {
                    'openBlock__description': true,
                    'openBlock__description-close': this.status
                }
            },
            classNum() {
                return {
                    'openBlock__label-num': true,
                    'act-num': this.status
                }
            },
            classLabel() {
                return {
                    'openBlock__label': true,
                    'act-label': this.status
                }
            }
        },
        methods: {

        }
    }
</script>

<style lang="scss" scoped>
  .openBlock {
    width: 100%;

    &__label {
      display: flex;
      justify-content: space-between;
      background-color: #332950;
      border-radius: 5px;
      padding: 10px 8px;
      margin-bottom: 5px;
      box-shadow: 0 4px 22px rgba(0, 0, 0, 0.15);
      transition: box-shadow .3s linear;
      cursor: url('/coursor-hover.png') 4 4, pointer;

      &.act-label {
        box-shadow: 0 4px 4px rgba(0, 0, 0, 0.08);

        .openBlock__label-content {
          color: #fff;
        }

        .openBlock__label-arrow {
          transform: rotate(90deg);

          svg path {
            fill: #fff;
          }
        }
      }

      &-left {
        display: flex;
        align-items: flex-end;
      }

      &-arrow {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 60px;
        width: 60px;
        transform: rotate(-90deg);
        transition: transform .3s linear;

        svg {
          height: 18px;
          width: 18px;

          path {
            transition: fill .3s linear;
            fill: #7C49F4;
          }
        }
      }

      &-num {
        font-family: 'Open Sans', sans-serif;
        font-weight: 800;
        font-size: 64px;
        line-height: 60px;
        color: #B08EFF; /* цвет текста для всех браузеров */
        -webkit-text-fill-color: transparent;
        -webkit-text-stroke: 1px #B08EFF;
        transition: all .3s linear;

        &.act-num {
          color: #fff; /* цвет текста для всех браузеров */
          -webkit-text-fill-color: transparent;
          -webkit-text-stroke: 1px #fff;
        }
      }

      &-content {
        color: #7C49F4;
        margin: 0 45px 0;
        font-style: normal;
        font-weight: normal;
        font-size: 32px;
        line-height: 36px;
        transition: all .3s linear;
      }
    }

    &__description {
      padding: 25px 10px 45px;
      display: flex;
      flex-direction: column;
      align-items: flex-end;
      box-sizing: border-box;
      transition: all .3s linear;
      max-height: 400px;
      overflow: hidden;

      &-close {
        max-height: 0;
        padding: 0 10px;
      }

      &-text {
        color: #fff;
        font-weight: 300;
        font-size: 24px;
        line-height: 148.8%;
      }

      &-button {
        padding: 8px 30px;
        color: #7C49F4;
        border: none;
        background: none;
        font-size: 24px;
        line-height: 148.8%;
        cursor: url('/coursor-hover.png') 4 4, auto;

        &:hover {
          text-decoration: underline;
        }
      }
    }
  }

  @media only screen and (max-width: 575px) {
    .openBlock {
      padding: 0 15px;

      &__label-left {
        align-items: center;
      }

      &__label-num {
        display: none;
      }

      &__label-content {
        font-size: 24px;
        line-height: 28px;
        max-width: 217px;
        margin: 0;
      }

      &__label-num {
        font-size: 28px;
      }
    }
  }
</style>
