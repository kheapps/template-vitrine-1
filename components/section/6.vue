<template>
  <div
    class="w-full py-32 px-5 md:px-20 flex justify-center items-center relative"
  >
    <div class="img-bg clipped absolute w-full h-full">
      <img
        class="absolute top-0 left-0 w-full h-full object-cover"
        src="https://cdn.pixabay.com/photo/2020/02/02/17/07/living-room-modern-tv-4813591_960_720.jpg"
        alt=""
      />
    </div>
    <div
      class="card w-fit py-32 px-16 md:px-32 rounded-xl shadow-xl flex flex-col justify-center items-center bg-emerald-50/80 z-10"
    >
      <h1 class="title">Titre section 5</h1>
      <div class="sized-box h-10"></div>
      <div class="content w-full flex flex-col items-center">
        <h3>Sous-titre section</h3>
        <div class="grid grid-cols-1 gap-5">
          <ExpertiseItem v-for="(exp, ind) in items" :key="ind" :item="exp" />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const items = [
  {
    logo: "fa6-regular:handshake",
    description: "Collaboration en total transparence",
  },
  {
    logo: "material-symbols:check-circle-outline-rounded",
    description: "Services complets pour valoriser vos biens",
  },
  {
    logo: "bi:building",
    description: "Experts en gestion locative professionnelle",
  },
];
</script>

<style scoped>
.clipped::before,
.clipped::after {
  content: "";
  @apply bg-light w-full h-14 md:h-20 absolute left-0 z-10;
}

.clipped::before {
  top: 0;
  clip-path: polygon(0 0, 100% 0, 0 100%);
}

.img-bg.clipped::after {
  bottom: 0;
  clip-path: polygon(0 0, 0 100%, 100% 100%);
}
</style>
