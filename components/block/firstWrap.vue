<template>
  <div class="first-wrap">
    <div class="fon" id="fon"></div>
    <first-block class="dt-block"/>
    <first-block-mobile class="mob-block"/>
    <second-block/>
    <div class="arrow" @click="scrollArrow">
      <div class="arrow__first"></div>
      <div class="arrow__second"></div>
    </div>
  </div>
</template>

<script>
    import firstBlock from "./firstBlock";
    import firstBlockMobile from "./firstBlockMobile";
    import secondBlock from "./secondBlock";

    export default {
        name: "first-wrap",
        components: {firstBlock, firstBlockMobile, secondBlock},
        mounted() {
            VANTA.NET({
                el: '#fon',
                color: 0x5D2CFF,
                backgroundColor: 0x221B37,
                points: 5.00,
                maxDistance: 16.00,
                spacing: 13.00
            });
        },
        methods: {
            scrollArrow() {
                var obj = document.querySelector('.third-block');

                obj.scrollIntoView({
                    behavior: "smooth",
                    block: "start"
                });
            }
        }
    }
</script>

<style lang="scss">
  .__layuot {
    background: #221B37;
    cursor: url('/coursor.png') 4 4, auto;
    font-family: 'Comfortaa', sans-serif;
  }

  .arrow {
    $size: 50px;

    height: $size;
    width: $size;
    border: 1px solid #0BFFB6;
    border-radius: 100%;
    margin: 0 auto;
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: url('/coursor-hover.png') 4 4, auto;
    box-shadow: 0 0 5px 1px #0BFFB6;
    animation: shadow 1s ease-in-out infinite;

    @keyframes shadow {
      0% {
        box-shadow: 0 0 5px 1px #0BFFB6;
      }
      50% {
        box-shadow: 0 0 1px 0 #0BFFB6;
      }
      100% {
        box-shadow: 0 0 5px 1px #0BFFB6;
      }
    }

    div {
      position: absolute;
      $border-arrow: 1px solid #0BFFB6;

      border: {
        bottom: $border-arrow;
        right: $border-arrow;
      };
    }

    &__first {
      height: $size / 2.7;
      width: $size / 2.7;
      transform: translateY(-5px) rotate(45deg) scale(0.9);
      animation: push 1s ease-in-out infinite;
    }

    &__second {
      height: $size / 2.2;
      width: $size / 2.2;
      transform: translateY(0) rotate(45deg);
      animation: push-2 1s ease-in-out infinite;
    }

    @keyframes push {
      30% {
        transform: translateY(-5px) rotate(45deg) scale(0.9);
      }
      60% {
        transform: translateY(-10px) rotate(45deg) scale(1);
      }
      100% {
        transform: translateY(-5px) rotate(45deg) scale(0.9);
      }
    }

    @keyframes push-2 {
      30% {
        transform: translateY(0) rotate(45deg);
      }
      60% {
        transform: translateY(-7px) rotate(45deg);
      }
      100% {
        transform: translateY(0) rotate(45deg);
      }
    }

  }

  #fon {
    position: absolute;
    top: 0;
    width: 100%;
    height: 100%;
    z-index: -1;
  }

  .first-wrap {
    position: relative;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  .mob-block {
    display: none;
  }

  @media only screen and (min-width: 992px) and (max-width: 1200px) {

  }

  @media only screen and (min-width: 768px) and (max-width: 991px) {

  }

  @media only screen and (min-width: 576px) and (max-width: 767px) {

  }

  @media only screen and (max-width: 575px) {
    .dt-block {
      display: none;
    }

    .mob-block {
      display: block;
    }
  }
</style>
