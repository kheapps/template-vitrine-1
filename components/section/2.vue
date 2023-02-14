<template>
  <ImageSection :image-url="imageUrl">
    <template v-slot:title> Titre section 1 </template>
    <template v-slot:content>
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Cum sapiente
        distinctio placeat eligendi eaque velit mollitia corporis. Dolorem
        aperiam rem, sed quasi repellat blanditiis temporibus reprehenderit
        asperiores sint adipisci excepturi consectetur neque eius velit quidem
        veritatis labore iste, quisquam ea.
        <br />
        <br />
        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Repellendus
        amet eius sapiente exercitationem voluptas odio cupiditate ex nisi.
        Repudiandae itaque omnis recusandae soluta, expedita ea magni tempore
        fugit hic magnam!
      </p>
      <div class="w-full flex justify-center md:justify-start mt-10">
        <button class="cta" @click="goToContact">Nous contacter</button>
      </div>
    </template>
  </ImageSection>
</template>

<script setup lang="ts">
const imageUrl =
  "https://www.kan-location.com/wp-content/uploads/2022/03/126306341_l-scaled-e1644930113882-768x808.jpg";

function goToContact() {
  window.scrollTo({
    top: document.getElementById("contact")?.offsetTop,
    left: 0,
    behavior: "smooth",
  });
  // setActive(ind);
}
</script>

<style scoped>
/* .img-bg {
  background-image: url(https://www.kan-location.com/wp-content/uploads/2022/03/126306341_l-scaled-e1644930113882-768x808.jpg);
} */
</style>
