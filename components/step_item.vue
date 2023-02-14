<template>
  <div
    class="w-full mt-7 flex flex-col md:flex-row items-center md:items-start"
  >
    <div
      class="step-number shrink-0 py-2 px-5 md:mr-3 bg-emerald-700 flex justify-center items-center rounded-3xl shadow-md font-bold text-light"
    >
      {{ index }}
    </div>
    <div class="w-full flex flex-col items-center md:items-start">
      <h3 class="h-10 m-0 flex items-center font-semibold text-emerald-700">
        {{ step.title }}
      </h3>
      <p class="font-light">{{ step.description }}</p>
    </div>
  </div>
</template>

<script setup lang="ts">
const { step, index } = defineProps<{
  step: { title: String; description: String };
  index: number;
}>();
</script>

<style scoped></style>
