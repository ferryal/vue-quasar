<template>
  <div class="flex items-center justify-center job-card-icon">
    <component :is="job.icon" />
  </div>
  <div class="fs-24">{{ job.name }}</div>
</template>

<script setup>
defineProps(["job"]);
</script>

<style scoped>
.job-card-icon {
  background-color: rgba(255, 255, 255, 0.4);
  width: 56px;
  height: 56px;
  border-radius: 8px;
}
</style>
