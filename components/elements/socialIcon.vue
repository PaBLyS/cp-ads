<template>
  <div class="wrap">
    <ul class="wrap__list">
      <li class="wrap__list-elem">
        <a href="/">
          <img src="/social/fb.png">
        </a>
      </li>
      <li class="wrap__list-elem">
        <a href="/">
          <img src="/social/tw.png">
        </a>
      </li>
      <li class="wrap__list-elem">
        <a href="/">
          <img src="/social/inst.png">
        </a>
      </li>
      <li class="wrap__list-elem">
        <a href="/">
          <img src="/social/in.png">
        </a>
      </li>
      <li class="wrap__list-elem">
        <a href="/">
          <img src="/social/dou.png">
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
    export default {
        name: "socialIcon"
    }
</script>

<style lang="scss" scoped>
  .wrap {
    width: 100%;
    transform: translateX(100px);

    &__list {
      width: 100%;
      margin: 0;
      padding: 0;
      display: flex;
      align-items: center;
      justify-content: center;

      &-elem {
        list-style: none;
        margin-right: 25px;

        a {

          img {

          }
        }
      }
    }
  }
</style>
