<template>
  <ImageSection :image-url="imageUrl">
    <template v-slot:title> Titre section 4 </template>
    <template v-slot:content>
      <div class="">
        <h3 class="w-full font-semibold my-0">
          Une mise en place simple & rapide
        </h3>
        <div class="steps w-full flex flex-col">
          <StepItem
            v-for="(item, ind) in steps"
            :step="item"
            :index="ind + 1"
            :key="item.title + ':' + ind"
          />
        </div>
      </div>
    </template>
  </ImageSection>
</template>

<script setup lang="ts">
const imageUrl =
  "https://www.kan-location.com/wp-content/uploads/2022/03/132935647_l-768x573.jpg";

const steps = [
  {
    title: "Titre étape",
    description:
      "Lorem ipsum dolor sit amet consectetur adipisicing elit. Laboriosam, temporibus!",
  },
  {
    title: "Titre étape",
    description:
      "Lorem ipsum dolor sit amet consectetur adipisicing elit. Laboriosam, temporibus!",
  },
  {
    title: "Titre étape",
    description:
      "Lorem ipsum dolor sit amet consectetur adipisicing elit. Laboriosam, temporibus!",
  },
];
</script>

<style scoped></style>
