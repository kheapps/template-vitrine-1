<template>
  <div class="flex flex-col">
    <h1 class="relative title w-full">
      <slot name="title"></slot>
    </h1>
    <div class="image-section w-full">
      <div class="image-container">
        <img :src="imageUrl" alt="" />
      </div>
      <div class="content">
        <slot name="content"></slot>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const props = defineProps({
  imageUrl: String,
});

const { imageUrl } = props;
</script>

<style scoped></style>
