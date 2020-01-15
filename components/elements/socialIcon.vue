<template>
  <div class="socialIcon">
    <ul class="socialIcon__list">
      <li class="socialIcon__list-elem">
        <a href="/">
          <img src="/social/fb.png">
        </a>
      </li>
      <li class="socialIcon__list-elem">
        <a href="/">
          <img src="/social/tw.png">
        </a>
      </li>
      <li class="socialIcon__list-elem">
        <a href="/">
          <img src="/social/inst.png">
        </a>
      </li>
      <li class="socialIcon__list-elem">
        <a href="/">
          <img src="/social/in.png">
        </a>
      </li>
      <li class="socialIcon__list-elem">
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
  .socialIcon {
    width: 100%;
    margin: 35px 0;

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
          cursor: url('/coursor-hover.png') 4 4, default;
        }
      }
    }
  }
</style>
