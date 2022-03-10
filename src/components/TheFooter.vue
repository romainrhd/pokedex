<script setup>
import { ref } from "vue";

const currentYear = ref(new Date().getFullYear());
</script>

<template>
  <footer class="container flex justify-center mx-auto py-4">
    <div>Romzor - {{ currentYear }}</div>
  </footer>
</template>
