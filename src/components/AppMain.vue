<template>
  <div
    class="q-gutter-md"
    :class="{ 'mobile-body': $q.screen.xs, body: !$q.screen.xs }"
  >
    <div class="row justify-between items-center">
      <div class="col-lg-6 col-12 text-white">
        <Transition appear enter-active-class="animated slow fadeIn delay-3s">
          <div style="position: relative" class="q-mb-md">
            <div
              :class="{ 'text-color-green': !$q.screen.xs }"
              :style="{
                fontSize: '18px',
                width: 'fit-content',
                padding: '6px 12px',
                borderRadius: '8px',
                backgroundColor: $q.screen.xs ? '#8bc4ff' : '#fff',
              }"
            >
              풀타임, 파트타임
            </div>
            <ArrowDownIcon
              :style="{
                position: 'absolute',
                bottom: '-9px',
                left: '9px',
                color: $q.screen.xs ? '#8bc4ff' : '#fff',
              }"
            />
          </div>
        </Transition>
        <TransitionGroup
          appear
          enter-active-class="animated fadeInUp slower"
          leave-active-class="animated fadeOut"
        >
          <div class="flex items-center heading" v-if="headerShow">
            최고의 실력을 가진 외국인 인재를 찾고 계신가요?
          </div>
          <div class="sub-heading" v-if="headerShow">
            법률 및 인사관리 부담없이 1주일 이내에 원격으로 채용해보세요.
          </div>
        </TransitionGroup>
        <div class="description" v-if="!$q.screen.xs">
          개발자가 필요하신가요?
        </div>

        <div class="row q-gutter-xl q-mt-xl" v-if="!$q.screen.xs">
          <div class="info col" v-for="(info, index) in infos" :key="index">
            <q-separator color="white" />
            <div class="flex items-center heading">
              {{ info.heading }}
            </div>
            <div class="sub-heading opacity">
              {{ info.subHeading }}
            </div>
          </div>
        </div>
      </div>

      <div
        class="col-lg-5 col-xs-12 flex items-center justify-center"
        :class="{ 'q-mt-lg': $q.screen.xs }"
      >
        <UserCarousel />
      </div>

      <JobCarousel v-if="!$q.screen.xs" />
    </div>
  </div>
</template>

<script setup>
import ArrowDownIcon from "components/icons/ArrowDownIcon.vue";
import JobCarousel from "./Jobs/JobCarousel.vue";
import UserCarousel from "./Users/UserCarousel.vue";
import { ref, onMounted } from "vue";

const mainOptions = [
  {
    label: "채용",
    value: "채용",
  },
  {
    label: "해외 개발자 원격 채용",
    value: "해외 개발자 원격 채용",
  },
  {
    label: "외국인 원격 채용 (비개발 직군)",
    value: "외국인 원격 채용 (비개발 직군)",
  },
];

const infos = [
  {
    heading: "120만원",
    subHeading: "임금을 해당 국가를 기준으로 계산합니다.",
  },
  {
    heading: "최대 3회 인력교체",
    subHeading: "막상 채용해보니 맞지 않아도 걱정하지 마세요. ",
  },
  {
    heading: "평균 3일, 최대 10일",
    subHeading: "급하게 사람이 필요한 경우에도 빠른 채용이 가능합니다.",
  },
];
const mainDropdown = ref("채용");

const headerShow = ref(false);

onMounted(() => {
  headerShow.value = true;
});
</script>

<style scoped lang="scss">
.body {
  margin-top: 100px;

  .heading {
    font-size: 48px;
    font-weight: 900;
    line-height: 62.4px;
    text-align: left;
  }

  .sub-heading {
    margin-top: 20px;
    font-size: 24px;
    font-weight: 900;
    line-height: 34px;
    text-align: left;
  }

  .opacity {
    opacity: 0.7;
  }

  .description {
    margin-top: 20px;
    font-size: 18px;
    font-weight: 900;
    line-height: 27px;
    text-align: left;
    text-decoration: underline;
  }

  .info {
    margin-top: 60px;
    width: 150px;

    .heading {
      margin-top: 10px;
      font-size: 18px;
      font-weight: 900;
      line-height: 27px;
      text-align: left;
    }

    .sub-heading {
      margin-top: 10px;
      font-size: 16px;
      font-weight: 600;
      line-height: 24px;
      text-align: left;
    }
  }
}

.mobile-body {
  margin-top: 50px;

  .heading {
    font-size: 36px;
    line-height: 46.8px;
  }

  .sub-heading {
    margin-top: 10px;
    font-size: 18px;
    line-height: 27px;
  }

  .description {
    margin-top: 10px;
    font-size: 18px;
    font-weight: 900;
    line-height: 27px;
  }

  .info {
    margin-top: 60px;
    width: 150px;

    .heading {
      margin-top: 10px;
      font-size: 18px;
      font-weight: 900;
      line-height: 27px;
      text-align: left;
    }

    .sub-heading {
      margin-top: 10px;
      font-size: 16px;
      font-weight: 600;
      line-height: 24px;
      text-align: left;
    }
  }
}
</style>
