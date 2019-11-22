<template>
  <section>
    <b-container>
      <b-row>
        <b-col cols="4"
               v-for="(elem, index) in elements"
               :key="index"
               class="elem"
        >
          <crumb-point :imgUrl="elem.imgUrl" :content="elem.content"/>
        </b-col>
      </b-row>
    </b-container>
  </section>
</template>

<script>
    import crumbPoint from "../elements/crumbPoint";

    export default {
        name: "secondBlock",
        components: {crumbPoint},
        data() {
            return {
                elements: [
                    {
                        content: 'Build Your Career',
                        imgUrl: '/crumb-1.png'
                    },
                    {
                        content: 'Live Your Passion',
                        imgUrl: '/crumb-2.png'
                    },
                    {
                        content: 'Create  Our Futures',
                        imgUrl: '/crumb-3.png'
                    }
                ]
            }
        }
    }
</script>

<style lang="scss" scoped>

  .elem {
    padding: 0;
  }
</style>
