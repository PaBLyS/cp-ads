<template>
  <b-container class="container-wrap">
    <b-row v-for="(elem, index) in elements"
           :key="index">
      <open-block :index="index"
                  :label="elem.label"
                  :content="elem.content"/>
    </b-row>
  </b-container>
</template>

<script>
    import openBlock from "../elements/openBlock";

    export default {
        name: "thirdBlock",
        components: {openBlock},
        data() {
            return {
                elements: [
                    {
                        label: 'Affiliate Manager',
                        content: 'The Ad Masters is looking for Junior Node.js developers for an enterprise project in the eCommerce industry. The Ad Masters is seeking exceptionally.'
                    },
                    {
                        label: 'Senior Node.js Developer',
                        content: 'The Ad Masters is looking for Junior Node.js developers for an enterprise project in the eCommerce industry. The Ad Masters is seeking exceptionally.'
                    },
                    {
                        label: 'Media Buyer',
                        content: 'The Ad Masters is looking for Junior Node.js developers for an enterprise project in the eCommerce industry. The Ad Masters is seeking exceptionally.'
                    }

                ]
            }
        }
    }
</script>

<style lang="scss" scoped>
  .container-wrap {
    padding-top: 65px;
  }
</style>
