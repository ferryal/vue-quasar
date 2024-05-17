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

<style>
@import url("https://fonts.googleapis.com/css2?family=Macondo&family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&family=Quicksand:wght@300;400;500;600&display=swap");

html,
body {
  font-family: "Poppins", sans-serif !important;
}
</style>
