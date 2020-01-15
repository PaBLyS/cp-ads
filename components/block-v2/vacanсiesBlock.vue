<template>
  <b-container class="vacansiesBlock">
    <b-row>
      <b-col cols="4" v-for="(elem, index) in element"
             :key="`col-${index}`"
             class="vacansiesBlock__wrap">
        <div>
          <div class="vacansiesBlock__wrap-label">
            {{elem.label}}
          </div>
          <div v-for="(vac, i) in elem.vacansies"
               class="vacansiesBlock__wrap-content"
               :key="`vac-${i}`"
               v-if="i < elem.maxVisible">
            {{vac}}
            <nuxt-link to="/popup-form">
              <div class="vacansiesBlock__wrap-content-link">
                <div>Подать заявку</div>
                <span class="vacansiesBlock__wrap-content-circle"></span>
              </div>
            </nuxt-link>
          </div>

          <!-- Visible on mobile -->
<!--          <div @click="openBlock(true, index)"-->
<!--               v-if="elem.maxVisible === 4">-->
<!--            <div class="vacansiesBlock__buttonVisible mobile">-->
<!--              Посмотреть все вакансии-->
<!--            </div>-->
<!--          </div>-->
<!--          <div @click="openBlock(false, index)"-->
<!--               v-if="!(elem.maxVisible === 4)">-->
<!--            <div class="vacansiesBlock__buttonVisible mobile">-->
<!--              скрить вакансии-->
<!--            </div>-->
<!--          </div>-->
          <!-- /Visible on mobile -->

        </div>
      </b-col>
    </b-row>

    <!-- Visible on desktop -->
    <b-row class="justify-content-center">
      <b-col cols="4" @click="openBlockAll(true)"
             v-if="visibleAll">
        <div class="vacansiesBlock__buttonVisible desktop">
          Посмотреть все вакансии
        </div>
      </b-col>
      <b-col cols="4" @click="openBlockAll(false)"
             v-if="!visibleAll">
        <div class="vacansiesBlock__buttonVisible desktop">
          скрить вакансии
        </div>
      </b-col>
    </b-row>
    <!-- /Visible on desktop -->

  </b-container>
</template>

<script>
    export default {
        name: "vacansiesBlock",
        data() {
            return {
                element: [
                    {
                        label: 'Business Development',
                        vacansies: [
                            'Project Manager ',
                            'Junior Project Manager',
                            'Business Analyst',
                            'Junior Product Manager',
                            'Business Development Manager',
                            'DevOps',
                            'Executive Assistant to the CEO'
                        ],
                        maxVisible: 4
                    },
                    {
                        label: 'Marketing & HR',
                        vacansies: [
                            'Junior Media Buyer',
                            'Affiliate Manager',
                            'Facebook Media Buyer',
                            'HR Manager',
                            'Social Media Manager (SMM)',
                            'IT Recruiter',
                            'Office Manager'
                        ],
                        maxVisible: 4
                    },
                    {
                        label: 'Developers',
                        vacansies: [
                            'Junior Node JavaScript Engineer',
                            'Python Automation Engineer',
                            'WordPress Developer',
                            'Node JavaScript Engineer',
                            'Web Manual QA Engineer',
                            'Senior React.js Developer'
                        ],
                        maxVisible: 4
                    }
                ]
            }
        },
        computed: {
            visibleAll() {
                let status = true;
                this.element.forEach((elem) => {
                    if (!(elem.maxVisible === 4)) {
                        status = false;
                    }
                });
                return status;
            }
        },
        methods: {
            openBlockAll(e) {
                if (e) {
                    this.element.forEach((elem) => {
                        elem.maxVisible = 1000;
                    })
                } else {
                    this.element.forEach((elem) => {
                        elem.maxVisible = 4;
                    })
                }
            },
            openBlock(e, index) {
                e ? this.element[index].maxVisible = 1000 : this.element[index].maxVisible = 4;
            }
        }
    }
</script>

<style lang="scss" scoped>
  .vacansiesBlock {
    padding: 90px 0;

    &__buttonVisible {
      cursor: pointer;
      font-family: 'Open Sans', sans-serif;
      font-style: normal;
      font-weight: bold;
      font-size: 18px;
      line-height: 25px;
      text-align: center;
      text-transform: uppercase;
      color: #333333;
      border: 1px solid #39D4EC;
      background: transparent;
      border-radius: 4px;
      padding: 15px 0;
      width: 100%;
      margin: 30px 0;

      &:hover {
        background: linear-gradient(90deg, #35B5FC 0.42%, #39D5EB 100%);
      }
    }

    &__wrap {
      overflow: hidden;

      &-label {
        color: #ffffff;
        font-family: 'Open Sans', sans-serif;
        font-style: normal;
        font-weight: bold;
        font-size: 24px;
        line-height: 45px;
        background: linear-gradient(90deg, #35B5FC 0.42%, #39D5EB 100%);
        border-radius: 10px 10px 0 0;
        padding: 5px 10px;
      }

      &-content {
        padding: 5px 30px;
        font-family: 'Open Sans', sans-serif;
        font-style: normal;
        font-weight: normal;
        font-size: 24px;
        line-height: 45px;
        border: {
          bottom: 1px solid #35B5FC;
          left: 1px solid #35B5FC;
          right: 1px solid #35B5FC;
        };
        overflow: hidden;
        white-space: nowrap;
        position: relative;

        &:hover {
          .vacansiesBlock__wrap-content-link {
            left: 0;

            .vacansiesBlock__wrap-content-circle {
              height: 100%;
            }
          }
        }

        &-link {
          position: absolute;
          top: 0;
          left: -100%;
          width: 100%;
          height: 100%;
          display: flex;
          align-items: center;
          justify-content: center;
          background: linear-gradient(90deg, #35B5FC 0.42%, #39D5EB 100%);
          font-family: 'Helvetica LT', sans-serif;
          font-style: normal;
          font-weight: bold;
          font-size: 24px;
          line-height: 45px;
          color: #FFFFFF;
          transition: left .6s ease-in;
          cursor: pointer;
        }

        &-circle {
          $size-circle: 48px;

          height: $size-circle;
          width: $size-circle;
          background: #39D5EB;
          position: absolute;
          right: 0;
          transform: translateX(50%);
          border-radius: 100%;
        }
      }

      &-bottom {

      }
    }
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
