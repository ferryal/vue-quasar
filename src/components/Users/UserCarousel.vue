<template>
  <UserCardTooltip />
  <Transition appear enter-active-class="animated fadeIn">
    <div style="position: relative">
      <Swiper
        class="flex justify-center"
        ref="swiperRef"
        effect="cards"
        slidesPerView="auto"
        :modules="[EffectCards]"
        :grabCursor="true"
        :centeredSlides="true"
        :initialSlide="1"
        :cardsEffect="{
          perSlideOffset: $q.screen.xs ? 10 : 21,
          perSlideRotate: 0,
          rotate: false,
          slideShadows: false,
        }"
        @swiper="onSwiper"
      >
        <SwiperSlide v-for="i in 3" :key="i">
          <UserCard />
        </SwiperSlide>
      </Swiper>
      <q-btn
        flat
        round
        class="prev_btn"
        :class="{ mobile: $q.screen.xs }"
        @click="swiperPrevSlide"
      >
        <CaretLeftIcon />
      </q-btn>
      <q-btn
        flat
        round
        class="next_btn"
        :class="{ mobile: $q.screen.xs }"
        @click="swiperNextSlide"
      >
        <CaretRightIcon />
      </q-btn>
    </div>
  </Transition>

  <template v-if="$q.screen.xs">
    <Transition appear enter-active-class="animated slow fadeInUp">
      <div class="q-my-md">
        <div class="row q-gutter-y-sm text-white">
          <div class="col">
            <div class="flex items-center mobile-checked-text">
              <CheckboxIcon class="check-icon" />
              <div>한국어 능력</div>
            </div>
          </div>
          <div class="col">
            <div class="flex items-center mobile-checked-text">
              <CheckboxIcon class="check-icon" />
              <div>업무 수행 능력</div>
            </div>
          </div>
        </div>

        <div class="row q-gutter-y-sm text-white">
          <div class="col">
            <div class="flex items-center mobile-checked-text">
              <CheckboxIcon class="check-icon" />
              <div>겸업 여부</div>
            </div>
          </div>
          <div class="col">
            <div class="flex items-center mobile-checked-text">
              <CheckboxIcon class="check-icon" />
              <div>평판 조회</div>
            </div>
          </div>
        </div>
      </div>
    </Transition>
    <Transition
      appear
      enter-active-class="animated slow fadeInUp"
      class="q-mb-md"
    >
      <div class="text-white" style="font-size: 14px">
        개발자가 필요하신가요?
      </div>
    </Transition>
  </template>
</template>

<script setup>
import { ref } from "vue";
import { EffectCards } from "swiper/modules";
import { Swiper, SwiperSlide } from "swiper/vue";
import UserCardTooltip from "./UserCardTooltip.vue";
import UserCard from "src/components/Users/UserCard.vue";
import CaretRightIcon from "src/components/icons/CaretRightIcon.vue";
import CaretLeftIcon from "src/components/icons/CaretLeftIcon.vue";
import CheckboxIcon from "src/components/icons/CheckboxIcon.vue";

const swiperInstance = ref();

const onSwiper = (swiper) => {
  swiperInstance.value = swiper;
};
const swiperNextSlide = () => {
  console.log(swiperInstance.value);
  swiperInstance.value.slideNext();
};

const swiperPrevSlide = () => {
  swiperInstance.value.slidePrev();
};
</script>

<style scoped lang="scss">
.swiper {
  width: 100%;
  height: auto;
  margin-top: 24px;
}

.swiper-slide {
  display: flex;
  align-items: center;
  justify-content: center;
}

.swiper-slide-prev,
.swiper-slide-next {
  opacity: 1;
}

.swiper-button-next:after,
.swiper-button-prev:after {
  font-size: 32px !important;
  color: white !important;
}
.prev_btn {
  position: absolute;
  left: 0px;
  top: 50%;
  z-index: 1;

  &.mobile {
    position: absolute;
    left: 20px;
    top: 50%;
    z-index: 1;
  }
}
.next_btn {
  position: absolute;
  right: 0px;
  top: 50%;
  z-index: 1;

  &.mobile {
    position: absolute;
    right: 20px;
    top: 50%;
    z-index: 1;
  }
}

.prev_btn:hover,
.next_btn:hover {
  background-color: #08a1cb;
}

.mobile-checked-text {
  font-size: 14px;
  font-weight: 900;
  line-height: 24px;
  text-align: left;
}
.check-icon {
  height: 20px;
  width: 20px;
  margin-right: 5px;
}
</style>
