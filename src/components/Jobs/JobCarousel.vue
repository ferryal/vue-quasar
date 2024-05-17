<template>
  <Transition
    appear
    enter-active-class="animated fadeIn slower delay-2s"
    leave-active-class="animated fadeOut"
  >
    <Swiper
      :modules="[Autoplay]"
      :slidesPerView="4.5"
      :spaceBetween="10"
      :autoplay="{
        delay: 5000,
        disableOnInteraction: false,
      }"
    >
      <SwiperSlide v-for="(job, index) in jobs" :key="index">
        <JobCard :job="job" />
      </SwiperSlide>
    </Swiper>
  </Transition>
</template>

<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Autoplay } from "swiper/modules";
import MarketingIcon from "components/icons/MarketingIcon.vue";
import ImageIcon from "components/icons/ImageIcon.vue";
import BoxIcon from "components/icons/BoxIcon.vue";
import TargetIcon from "components/icons/TargetIcon.vue";
import CallIcon from "components/icons/CallIcon.vue";
import PresentationIcon from "components/icons/PresentationIcon.vue";
import JobCard from "src/components/Jobs/JobCard.vue";

const jobs = [
  {
    name: "해외 마케팅",
    icon: MarketingIcon,
  },
  {
    name: "퍼블리셔",
    icon: ImageIcon,
  },
  {
    name: "캐드원(제도사)",
    icon: BoxIcon,
  },
  {
    name: "해외 세일즈",
    icon: TargetIcon,
  },
  {
    name: "해외 CS",
    icon: CallIcon,
  },
  {
    name: "해외 마케팅",
    icon: PresentationIcon,
  },
];
</script>

<style scoped>
.swiper {
  width: 100%;
  height: 100%;
  margin-top: 80px;
}

.swiper-slide {
  display: flex;
  align-items: center;
  padding-left: 16px;
  padding-right: 16px;
  border-radius: 12px;
  gap: 24px;
  height: 88px !important;
  color: white;
  background-color: rgba(255, 255, 255, 0.2);
}
</style>
