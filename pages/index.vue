<template>
  <section>

    <!-- --- version 1 --- -->
    <first-wrap v-if="testVersion === 1"/>
    <third-block v-if="testVersion === 1" class="third-block"/>
    <diagram-block v-if="testVersion === 1"/>
    <form-block v-if="testVersion === 1"/>

    <!-- --- version 2 --- -->
    <first-block-v2 v-if="testVersion === 2"/>
    <second-wrap-v2 v-if="testVersion === 2"/>
    <office-block-v2 v-if="testVersion === 2"/>
    <about-us-v2 v-if="testVersion === 2"/>
    <custom-footer-v2 v-if="testVersion === 2"/>

  </section>
</template>

<script>
    import firstWrap from "../components/block/firstWrap";
    import thirdBlock from "../components/block/thirdBlock";
    import diagramBlock from "../components/block/diagramBlock";
    import formBlock from "../components/block/formBlock";
    import firstBlockV2 from "../components/block-v2/firstBlock";
    import secondWrapV2 from "../components/block-v2/secondWrap";
    import officeBlockV2 from "../components/block-v2/officeBlock";
    import aboutUsV2 from "../components/block-v2/aboutUs";
    import customFooterV2 from "../components/block-v2/customFooter";

    export default {
        components: {
            firstWrap,
            thirdBlock,
            formBlock,
            diagramBlock,
            firstBlockV2,
            secondWrapV2,
            officeBlockV2,
            aboutUsV2,
            customFooterV2
        },
        data() {
            return {
                testVersion: 2
            }
        }
    }
</script>

<style lang="scss">
  @media only screen and (min-width: 992px) and (max-width: 1200px) {

  }

  @media only screen and (min-width: 768px) and (max-width: 991px) {

  }

  @media only screen and (min-width: 576px) and (max-width: 767px) {

  }

  @media only screen and (max-width: 575px) {

  }
</style>
