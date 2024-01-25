<script setup lang="ts" generic="T extends keyof GlobalComponents">
import type { GlobalComponents } from 'vue';

const props = defineProps<{
  name: T extends `Icon${infer N}` ? N : never,
  size?: 16 | 24
}>();

const Icon = defineAsyncComponent(() => import(`~/components/icon/${props.name}.vue`));
</script>

<template>
  <component :is="Icon" />
</template>
