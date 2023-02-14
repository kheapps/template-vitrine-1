<template>
  <div
    class="relative h-screen w-full flex flex-col justify-center items-center text-light"
  >
    <div class="img-bg absolute w-full h-full">
      <img
        class="w-full h-full object-cover"
        src="https://cdn.pixabay.com/photo/2016/11/08/09/47/logs-1807830_960_720.jpg"
        alt=""
      />
    </div>
    <div
      class="content h-full w-full flex flex-col justify-center items-center bg-gray-500/20 z-10"
    >
      <h1
        class="title md:pb-7 !text-white !text-3xl md:!text-7xl after:bg-emerald-100"
      >
        Lorem, ipsum dolor
      </h1>
      <h3
        class="text-light px-5 text-base md:text-3xl font-semibold text-center"
      >
        Lorem ipsum dolor sit amet consectetur adipisicing.
      </h3>
      <div class="absolute bottom-0">
        <div class="flex flex-col justify-center items-center">
          <Icon
            name="material-symbols:keyboard-arrow-down-rounded"
            class="bouncing h-10 w-10"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped>
.img-bg {
  -webkit-filter: blur(3px) grayscale(70%) brightness(45%);
  filter: grayscale(70%) brightness(45%);
  transition: all 250ms ease;
}

.bouncing {
  animation: bounce 1.5s infinite;
}

@keyframes bounce {
  0%,
  20%,
  70%,
  80%,
  100% {
    transform: translateY(0);
  }
  30% {
    transform: translateY(-15px);
  }
  40% {
    transform: translateY(-3px);
  }
  50% {
    transform: translateY(-13px);
  }
}
</style>
