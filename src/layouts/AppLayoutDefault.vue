<script setup>
import TheHeader from "@/components/TheHeader.vue";
import TheFooter from "@/components/TheFooter.vue";
</script>

<template>
  <div class="flex flex-col min-h-screen">
    <TheHeader />
    <div class="flex-grow px-4 py-4 bg-gray-100">
      <div class="container mx-auto">
        <slot />
      </div>
    </div>
    <TheFooter />
  </div>
</template>
