<script setup>
defineProps([ 'data' ]);
</script>

<template>
  <li v-if="!data.done">
    <strong>{{ data.title }}</strong><br>
  </li>
</template>
