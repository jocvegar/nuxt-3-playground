<script setup>
useHead({
  titleTemplate: "My App - %s",
  viewport: "width=device-width, initial-scale=1, maximum-scale=1",
  charset: "utf-8",
  meta: [{ name: "description", content: "My amazing site." }],
  bodyAttrs: {
    id: "main",
  },
  link: [
    { rel: "stylesheet", href: "https://cdn.simplecss.org/simple.min.css" },
  ],
});
</script>

<template>
  <div>
    <Hola />
  </div>
</template>

<style>
#main {
  margin-top: 5em;
}
</style>
