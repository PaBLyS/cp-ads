<template>
  <div class="wrap">
    <div :class="classLabel" @click="changeStatus">
      <div class="wrap__label-left">
        <span :class="classNum">{{index + 1}}</span>
        <p class="wrap__label-content">{{label}}</p>
      </div>
      <div class="wrap__label-arrow">
        <svg x="0px" y="0px"
             viewBox="0 0 41.999 41.999" xml:space="preserve">
          <path d="M36.068,20.176l-29-20C6.761-0.035,6.363-0.057,6.035,0.114C5.706,0.287,5.5,0.627,5.5,0.999v40
            c0,0.372,0.206,0.713,0.535,0.886c0.146,0.076,0.306,0.114,0.465,0.114c0.199,0,0.397-0.06,0.568-0.177l29-20
            c0.271-0.187,0.432-0.494,0.432-0.823S36.338,20.363,36.068,20.176z"></path>
        </svg>
      </div>
    </div>
    <div :class="classDescription">
      <p class="wrap__description-text">{{content}}</p>
      <button class="wrap__description-button">Read more</button>
    </div>
  </div>
</template>

<script>
    export default {
        name: "openBlock",
        props: {
            index: Number,
            label: String,
            content: String
        },
        data() {
            return {
                status: true
            }
        },
        computed: {
            classDescription() {
                return {
                    'wrap__description': true,
                    'wrap__description-close': this.status
                }
            },
            classNum() {
                return {
                    'wrap__label-num': true,
                    'act-num': this.status
                }
            },
            classLabel() {
                return {
                    'wrap__label': true,
                    'act-label': this.status
                }
            }
        },
        methods: {
            changeStatus() {
                this.status = !this.status
            }
        }
    }
</script>

<style lang="scss" scoped>
  .wrap {
    width: 100%;

    &__label {
      display: flex;
      justify-content: space-between;
      background-color: #332950;
      padding: 10px 8px;
      margin-bottom: 5px;
      box-shadow: 0 4px 22px rgba(0, 0, 0, 0.15);
      transition: box-shadow .5s ease-in-out;
      cursor: url('/coursor-hover.png') 4 4, pointer;

      &.act-label {
        box-shadow: 0 4px 4px rgba(0, 0, 0, 0.08);

        .wrap__label-content {
          color: #fff;
        }

        .wrap__label-arrow{
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
        transition: transform .5s ease-in-out;

        svg {
          height: 18px;
          width: 18px;

          path {
            transition: fill .5s ease-in-out;
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
        transition: all .3s;

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
        transition: all .3s;
      }
    }

    &__description {
      padding: 25px 10px 45px;
      display: flex;
      flex-direction: column;
      align-items: flex-end;
      box-sizing: border-box;
      transition: all .3s;
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
</style>
