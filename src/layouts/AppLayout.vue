<script setup>
import AppLayoutDefault from "./AppLayoutDefault.vue";
import { markRaw, ref, watch } from "vue";
import { useRoute } from "vue-router";

const layout = ref();
const route = useRoute();
layout.value = markRaw(AppLayoutDefault);

watch(
  () => route.meta?.layout,
  async (metaLayout) => {
    try {
      // /* @vite-ignore */ if you are using vite
      const component =
        metaLayout && (await import(/* @vite-ignore */ `./${metaLayout}.vue`));
      layout.value = markRaw(component?.default || AppLayoutDefault);
    } catch (e) {
      layout.value = markRaw(AppLayoutDefault);
    }
  },
  { immediate: true }
);
</script>

<template>
  <component :is="layout">
    <slot />
  </component>
</template>
