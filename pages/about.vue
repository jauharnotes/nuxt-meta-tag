<script setup lang="ts">
useHead({
  title: "Johar App | About",
  meta: [{ name: "description", content: "My amazing site." }],
  bodyAttrs: {
    class: "test",
  },
  script: [{ innerHTML: "console.log('Hello world')" }],
});
</script>

<template>
  <section>
    <p>This page will be displayed at the /about route.</p>
  </section>
</template>
