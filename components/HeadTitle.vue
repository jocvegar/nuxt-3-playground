<script setup>
defineProps({
  title: { type: String, required: false, default: "Jose Vega" },
});
</script>

<template>
  <Head>
    <Title>{{ title }}</Title>
  </Head>
</template>
