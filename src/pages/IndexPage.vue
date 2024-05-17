<template>
  <q-page class="background-gradient">
    <div
      :class="{ container: !$q.screen.xs, 'container-mobile': $q.screen.xs }"
    >
      <AppHeader />
      <AppMain />
    </div>
  </q-page>
</template>

<script setup>
import AppHeader from "components/AppHeader.vue";
import AppMain from "components/AppMain.vue";
</script>

<style scoped>
.background-gradient {
  background: url("img/pattern.svg"),
    linear-gradient(151.17deg, #26c2b9 8.69%, #288be7 126.06%);
  background-position: center; /* Center the image */
  background-repeat: no-repeat; /* Do not repeat the image */
  background-size: cover; /* Resize the background image to cover the entire container */
  background-blend-mode: color-burn;
}

.container-mobile {
  padding: 0 7% !important;
}
</style>
