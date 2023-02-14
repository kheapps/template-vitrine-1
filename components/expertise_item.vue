<template>
  <div class="flex flex-col justify-center items-center mt-2">
    <Icon :name="item.logo" class="text-3xl mb-3 shrink-0 text-emerald-700" />
    <p class="text-center">{{ item.description }}</p>
  </div>
</template>

<script setup lang="ts">
const { item } = defineProps<{ item: { logo: string; description: string } }>();
</script>

<style scoped></style>
