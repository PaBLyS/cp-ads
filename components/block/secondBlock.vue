<template>
  <section>
    <b-container>
      <b-row>
        <b-col md="4" cols="12"
               v-for="(elem, index) in elements"
               :key="index"
               class="elemCrumb"
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
  .elemCrumb {
    padding: 0;
  }
</style>
