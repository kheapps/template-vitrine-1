<template>
  <div class="test w-full min-h-screen flex flex-col bg-light">
    <header id="header"></header>

    <div id="body" class="w-full flex flex-col justify-between items-center">
      <div class="w-full flex justify-center items-center">
        <div class="w-full max-w-7xl" id="page-container">
          <NuxtPage class="page z-20" page-key="static" />
        </div>
      </div>
    </div>

    <MyFooter />
  </div>
</template>

<script setup lang="ts"></script>

<style scoped></style>
