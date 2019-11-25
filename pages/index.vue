<template>
    <section>
        <div class="first-wrap">
            <canvas class="fon" id="fon"></canvas>
            <first-block/>
            <second-block/>
            <div class="arrow" @click="scrollArrow">
                <div class="arrow__first"></div>
                <div class="arrow__second"></div>
            </div>
        </div>
        <third-block class="third-block"/>
        <diagram-block/>
        <form-block/>
        <b-container class="social-container">
            <b-row class="justify-content-end">
                <b-col cols="9">
                    <social-icon/>
                </b-col>
            </b-row>
        </b-container>
    </section>
</template>

<script>
    import firstBlock from "../components/block/firstBlock";
    import secondBlock from "../components/block/secondBlock";
    import thirdBlock from "../components/block/thirdBlock";
    import diagramBlock from "../components/block/diagramBlock";
    import formBlock from "../components/block/formBlock";

    import socialIcon from "../components/elements/socialIcon";

    export default {
        components: {firstBlock, secondBlock, thirdBlock, formBlock, socialIcon, diagramBlock},
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
    body {
        background: #221B37;
        cursor: url('/coursor.png') 4 4, auto;
    }

    @media only screen and (min-width: 1921px) {
        .first-wrap {

            .section__row-img img {
                height: 130%;
                width: 130%;
                object-fit: contain;
            }

            .section__row-content {
                font-size: 38px;
                line-height: 42px;
            }

            .section__row-item2 {
                -webkit-box-flex: 0;
                flex: 0 0 40%;
                max-width: 40%;
            }

            .section__row-item1 {
                -webkit-box-flex: 0;
                flex: 0 0 39%;
                max-width: 39%;
            }

            .section__row-list li {
                font-size: 38px;
                line-height: 42px;

                &:before {
                    height: 30px;
                    width: 30px;
                    margin: 0 30px 0 50px;
                }
            }

            .container {
                max-width: 90%;

                .section__row-list {
                    justify-content: center;
                }
            }
        }
    }

    @media only screen and (min-width: 2170px) {
        .first-wrap {
            .section__row-item2 {
                -webkit-box-flex: 0;
                flex: 0 0 50%;
                max-width: 50%;
            }
        }
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
            height: $size/2.7;
            width: $size/2.7;
            transform: translateY(-5px) rotate(45deg) scale(0.9);
            animation: push 1s ease-in-out infinite;
        }

        &__second {
            height: $size/2.2;
            width: $size/2.2;
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

    .social-container {
        padding: 0 0 50px;
    }

    @media only screen and (min-width: 992px) and (max-width: 1200px) {

    }

    @media only screen and (min-width: 768px) and (max-width: 991px) {

    }

    @media only screen and (min-width: 576px) and (max-width: 767px) {

    }

    @media only screen and (max-width: 575px) {

    }
</style>
