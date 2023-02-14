<template>
  <div class="flex flex-col justify-center items-center">
    <h1 class="title px-5 py-5 border-emerald-900">Titre section 2</h1>
    <div class="content">
      <div class="grid grid-cols-1 md:grid-cols-3 gap-10">
        <AvantageItem
          v-for="(item, ind) in avantages"
          :key="item.title + ':' + ind"
          :item="item"
        />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const avantages = [
  {
    title: "Sérénité",
    icon: "logos:nuxt-icon",
    description:
      "Lorem ipsum dolor sit amet consectetur adipisicing elit. Explicabo accusamus quo nobis voluptas eaque?",
  },
  {
    title: "Rentabilité",
    icon: "logos:nuxt-icon",
    description:
      "Lorem ipsum dolor sit amet consectetur adipisicing elit. Explicabo accusamus quo nobis voluptas eaque? ",
  },
  {
    title: "Flexibilité",
    icon: "logos:nuxt-icon",
    description:
      "Lorem ipsum dolor sit amet consectetur adipisicing elit. Explicabo accusamus quo nobis voluptas eaque?",
  },
  {
    title: "Sécurité",
    icon: "logos:nuxt-icon",
    description:
      "Lorem ipsum dolor sit amet consectetur adipisicing elit. Explicabo accusamus quo nobis voluptas eaque?",
  },
  {
    title: "Assurance",
    icon: "logos:nuxt-icon",
    description:
      "Lorem ipsum dolor sit amet consectetur adipisicing elit. Explicabo accusamus quo nobis voluptas eaque?",
  },
  {
    title: "Valorisation",
    icon: "logos:nuxt-icon",
    description:
      "Lorem ipsum dolor sit amet consectetur adipisicing elit. Explicabo accusamus quo nobis voluptas eaque?",
  },
];
</script>

<style scoped></style>
