<template>
  <section class="thirdBlock">
      <b-container class="thirdBlock-wrap">
        <b-row v-for="(elem, index) in elements"
            :key="index">
        <open-block :index="index"
                    :label="elem.label"
                    :content="elem.content"
                    :status="elem.status"
                    :changeOpen="changeOpen"/>
        </b-row>
    </b-container>
  </section>
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
                        status: true,
                        label: 'Affiliate Manager',
                        content: 'The Ad Masters is looking for Junior Node.js developers for an enterprise project in the eCommerce industry. The Ad Masters is seeking exceptionally.'
                    },
                    {
                        status: true,
                        label: 'Senior Node.js Developer',
                        content: 'The Ad Masters is looking for Junior Node.js developers for an enterprise project in the eCommerce industry. The Ad Masters is seeking exceptionally.'
                    },
                    {
                        status: true,
                        label: 'Media Buyer',
                        content: 'The Ad Masters is looking for Junior Node.js developers for an enterprise project in the eCommerce industry. The Ad Masters is seeking exceptionally.'
                    }

                ]
            }
        },
        methods: {
            changeOpen(index) {
                this.elements.forEach((elem, i) => {
                    elem.status = i !== index;
                });

            }
        }
    }
</script>

<style lang="scss" scoped>
  .thirdBlock {
      background: #221B37;
      
      &-wrap {
        padding-top: 65px;
      }
  }

</style>
