<script setup>
useHead({
  titleTemplate: "My App - %s",
  bodyAttrs: {
    id: "main",
  },
});
</script>

<template>
  <div class="bg-dark text-white pt-5">
    <div class="container">
      <Hola />
    </div>
  </div>
</template>

<style>
#main {
  font-weight: 500;
}
</style>
