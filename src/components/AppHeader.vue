<template>
  <div class="header q-gutter-md q-py-md">
    <div class="row justify-between items-center">
      <!-- Division 1: Logo and Site Name -->
      <div class="col-lg-4 col col-xs-6">
        <div class="flex items-center">
          <img
            alt="Main logo"
            src="~assets/page-logo.png"
            style="width: 20px; height: 20px"
          />
          <span class="text-white q-ml-xs text-weight-bold">hyperhire</span>
        </div>
      </div>

      <!-- Division 2: Main Dropdown and Label -->
      <div
        v-if="!$q.screen.xs"
        class="col-lg-4 col flex items-center justify-center"
      >
        <q-select
          v-model="mainDropdown"
          :options="mainOptions"
          behavior="menu"
          dense
          hide-bottom-space
          label-color="white"
          color="white"
          transition-show="flip-up"
          transition-hide="flip-down"
          options-selected-class="text-primary"
          input-class="text-white"
        />
        <div class="text-weight-bold q-ml-xl text-white">
          해외 개발자 활용 서비스
        </div>
      </div>

      <!-- Division 3: Inquiry Button -->
      <div
        v-if="!$q.screen.xs"
        class="col-lg-4 col flex items-center justify-end"
      >
        <q-btn unelevated color="white" text-color="primary" label="문의하기" />
      </div>

      <div v-if="$q.screen.xs" class="col-6 col-lg-4 flex justify-end">
        <q-icon name="remove" size="1rem" color="white" />
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

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
const mainDropdown = ref("채용");
</script>

<style scoped>
.header {
  height: 60px;
  width: 100%;
}
</style>
