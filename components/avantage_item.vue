<template>
  <div
    class="card flex flex-col justify-between md:justify-start items-center md:items-start bg-emerald-200/50 p-7 pb-9 rounded-xl hover:bg-emerald-100/70"
  >
    <Icon :name="item.icon" class="mb-3 h-10 w-10 shrink-0 text-7xl" />
    <div
      class="flex flex-col items-center md:items-start text-center md:text-left"
    >
      <h3 class="font-bold text-emerald-900">{{ item.title }}</h3>
      <p class="">{{ item.description }}</p>
    </div>
  </div>
</template>

<script setup lang="ts">
const { item } = defineProps<{
  item: { title: string; icon: string; description: string };
}>();
</script>

<style scoped>
.card {
  transition: all 250ms ease;
}
</style>
