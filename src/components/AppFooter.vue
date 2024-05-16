<template>
  <footer>
    <div class="container footer" :class="{ mobile: $q.screen.xs }">
      <div
        class="grid"
        :class="{
          'grid-cols-12': !$q.screen.xs,
          'grid-cols-2': $q.screen.xs,
        }"
        style="gap: 14px"
      >
        <div
          class="column text-weight-bolder"
          :class="{
            'col-span-2': $q.screen.xs,
            'col-span-4': !$q.screen.xs,
          }"
          style="gap: 16px"
        >
          <img
            alt="Hyperhire Logo"
            :src="LogoDark"
            style="width: 187px; height: 34px"
          />
          <div class="text-weight-bolder text-color-gray-shade-1">
            우리는 국가의 장벽을 넘어 최고의 인재를 매칭해드립니다.
          </div>

          <div class="text-color-gray">
            <div>010-0000-0000</div>
            <div>aaaaa@naver.com</div>
          </div>
        </div>

        <div
          v-for="(service, si) in services"
          :key="si"
          class="bg-white q-pa-md column q-mt-lg text-weight-bolder"
          :class="{
            'col-span-2': !$q.screen.xs,
          }"
          style="border-radius: 12px; gap: 16px"
        >
          <div class="column" style="gap: 12px">
            <div
              class="flex items-center justify-center"
              style="
                width: 40px;
                height: 40px;
                background-color: #eff1f6;
                border-radius: 8px;
              "
            >
              <component :is="service.icon" />
            </div>
            <div class="text-color-gray-shade-1 text-weight-bolder">
              {{ service.name }}
            </div>
          </div>
          <div class="text-color-gray flex items-center" style="gap: 8px">
            바로가기 <ArrowRightIcon />
          </div>
        </div>
      </div>

      <div
        class="grid"
        :class="{
          'grid-cols-12': !$q.screen.xs,
          'grid-cols-2': $q.screen.xs,
        }"
        :style="$q.screen.xs ? 'gap:36px' : 'gap: 14px'"
      >
        <div
          class="row text-weight-bolder"
          :class="{
            'col-span-2': $q.screen.xs,
            'col-span-4': !$q.screen.xs,
          }"
          style="gap: 16px"
        >
          <div class="column" style="gap: 8px">
            <div class="text-color-gray-shade-1 fs-12">상호명</div>
            <div class="column" style="gap: 4px">
              <div class="text-color-gray fs-13">하이퍼하이어</div>
              <div class="text-color-gray fs-13">
                Hyperhire India Private Limited
              </div>
            </div>
          </div>

          <div class="column" style="gap: 8px">
            <div class="text-color-gray-shade-1 fs-12">대표 CEO</div>
            <div class="column" style="gap: 4px">
              <div class="text-color-gray fs-13">김주현</div>
              <div class="text-color-gray fs-13">Juhyun Kim</div>
            </div>
          </div>
        </div>

        <div
          class="column q-mt-lg col-span-2 text-weight-bolder"
          style="gap: 8px"
        >
          <div class="text-color-gray-shade-1 fs-12">사업자등록번호 CIN</div>
          <div class="column" style="gap: 4px">
            <div class="text-color-gray fs-13">427-86-01187</div>
            <div class="text-color-gray fs-13">U74110DL2016PTC290812</div>
          </div>
        </div>

        <div
          class="column q-mt-lg text-weight-bolder"
          :class="{
            'col-span-2': $q.screen.xs,
            'col-span-6': !$q.screen.xs,
          }"
          style="gap: 8px"
        >
          <div class="text-color-gray-shade-1 fs-12">주소 ADDRESS</div>
          <div class="column" style="gap: 4px">
            <div class="text-color-gray fs-13">
              서울특별시 강남대로 479, 지하 1층 238호
            </div>
            <div class="text-color-gray fs-13">
              D-138, Street number 11, Jagjeet Nagar, North East Delhi, New
              Delhi, 110053 India
            </div>
          </div>
        </div>
      </div>

      <div class="text-color-gray text-weight-bolder fs-13">
        ⓒ {{ new Date().getFullYear() }} Hyperhire
      </div>
    </div>
  </footer>
</template>

<script setup>
import LogoDark from "assets/dark.png";
import ArrowRightIcon from "components/icons/ArrowRightIcon.vue";
import CodeIcon from "components/icons/CodeIcon.vue";
import UserIcon from "components/icons/UserIcon.vue";
import SettingIcon from "components/icons/SettingIcon.vue";
import KorIcon from "components/icons/KorIcon.vue";

const services = [
  {
    name: "해외 개발자 원격 채용",
    icon: CodeIcon,
  },
  {
    name: "외국인 원격 채용 (비개발)",
    icon: UserIcon,
  },
  {
    name: "한국어 가능 외국인 채용",
    icon: SettingIcon,
  },
  {
    name: "해외 개발자 활용 서비스",
    icon: KorIcon,
  },
];
</script>

<style scope lang="scss">
footer {
  background-color: #fbfbfb;
  padding-top: 80px;
  padding-bottom: 80px;

  &.mobile {
    padding-top: 64px;
    padding-bottom: 64px;
    padding-left: 16px;
    padding-right: 16px;
  }
}
</style>
