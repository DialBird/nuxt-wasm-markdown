<script setup>
definePageMeta({
  layout: "custom",
});
</script>

<template>
  <p>I'm {{ $route.params.id }}</p>
</template>