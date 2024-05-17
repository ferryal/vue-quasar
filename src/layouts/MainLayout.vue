<template>
  <q-layout view="lHr lpR lFr">
    <q-page-container>
      <router-view />
    </q-page-container>

    <AppFooter />
  </q-layout>
</template>

<script setup>
import AppFooter from "components/AppFooter.vue";
</script>
