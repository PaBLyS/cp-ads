<template>
  <div class="socialIcon">
    <ul class="socialIcon__list">
      <li class="socialIcon__list-elem">
        <a href="/">
          <img src="/socialV2/fb.png">
        </a>
      </li>
      <li class="socialIcon__list-elem">
        <a href="/">
          <img src="/socialV2/tw.png">
        </a>
      </li>
      <li class="socialIcon__list-elem">
        <a href="/">
          <img src="/socialV2/inst.png">
        </a>
      </li>
      <li class="socialIcon__list-elem">
        <a href="/">
          <img src="/socialV2/in.png">
        </a>
      </li>
      <li class="socialIcon__list-elem">
        <a href="/">
          <img src="/socialV2/dou.png">
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
      }
    }
  }
</style>
