<template>
  <div class="w-full flex flex-col justify-center items-center">
    <h1 class="title w-full">Contactez-nous</h1>
    <div class="content w-full flex flex-col items-center">
      <div
        class="row md:w-full mb-5 md:mx-20 flex flex-col md:flex-row justify-center items-start text-xl"
      >
        <div
          class="item flex justify-center items-center mb-3 md:mb-0 md:mr-10"
        >
          <Icon name="bi:telephone-fill" class="mr-3" />
          <p>06 12 34 56 78</p>
        </div>
        <div class="item flex justify-center items-center">
          <Icon name="ic:round-email" class="mr-3" />
          <p>email@email.com</p>
        </div>
      </div>
      <p class="md:w-2/3 mb-7 text-center md:text-lg font-light">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis dolor
        omnis hic quas consectetur ab praesentium assumenda eaque neque
        sapiente!
      </p>
      <form
        @submit.prevent=""
        class="w-full md:w-2/3 flex flex-col justify-center items-center"
      >
        <div class="row w-full flex flex-col md:flex-row m-3">
          <input
            type="text"
            name="nom"
            id="nom"
            placeholder="Nom"
            class="!m-0"
          />
          <div class="sized-box w-20 h-6"></div>
          <input
            type="email"
            name="email"
            id="email"
            placeholder="email@email.com"
            class="!m-0"
          />
        </div>
        <input
          type="tel"
          name="telephone"
          placeholder="06 12 34 56 78"
          id="telephone"
        />
        <textarea
          type="text"
          name="message"
          id="message"
          placeholder="Votre message..."
          rows="5"
          class="m-3"
        />
        <div class="w-full flex justify-end">
          <button type="submit" class="cta w-full md:w-fit md:!px-20 shadow-lg">
            Envoyer
          </button>
        </div>
      </form>
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped>
input,
textarea {
  @apply w-full
        m-3
        px-3
        py-2
        rounded-xl
        shadow-sm
        text-base
        font-normal
        text-gray-700
        bg-white bg-clip-padding
        border border-solid border-gray-300
        transition
        ease-in-out
        focus:text-gray-700 focus:bg-white focus:border-blue-600 focus:outline-none;
}

textarea {
  resize: none;
}
</style>
