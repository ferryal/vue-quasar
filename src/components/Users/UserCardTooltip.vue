<template>
  <Transition appear enter-active-class="animated fadeIn">
    <div style="position: relative; width: fit-content; margin: 0 auto">
      <div
        class="text-color-green bg-white flex items-center"
        style="
          font-size: 18px;
          width: fit-content;
          padding: 6px 12px;
          border-radius: 8px;
          gap: 8px;
        "
      >
        <DollarIcon />
        월 100만원
      </div>
      <ArrowDownIcon
        style="position: absolute; bottom: -9px; left: 50%; color: white"
      />
    </div>
  </Transition>
</template>

<script setup>
import ArrowDownIcon from "components/icons/ArrowDownIcon.vue";
import DollarIcon from "../icons/DollarIcon.vue";
</script>
