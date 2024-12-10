<script setup lang="ts">
import AppAlert from "~/components/AppAlert.vue";

useHead({
  titleTemplate: "%s - My Blog",
  meta: [
    { charset: "utf-8" },
    { name: "viewport", content: "width=device-width, initial-scale=1" },
    { hid: "og:site_name", property: "og:site_name", content: "My Blog" },
  ],
});
</script>

<template>
  <div>
    <h1>Welcome to the homepage</h1>
    <AppAlert> This is an auto-imported component </AppAlert>
  </div>
</template>
