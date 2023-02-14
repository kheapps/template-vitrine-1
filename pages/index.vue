<template>
  <div class="flex flex-col justify-between items-center h-full w-full">
    <MyHeader :nav-items="navItems" :active-section="currentSection" />

    <body class="grow w-full">
      <div class="sections w-full">
        <MySection id="landing" class="!py-0 px-0">
          <Section1 class="display" />
        </MySection>
        <MySection id="about"> <Section2 /> </MySection>
        <MySection id="avantages"> <Section3 /> </MySection>
        <MySection id="clients"> <Section4 /> </MySection>
        <MySection id="methode"> <Section5 /> </MySection>
        <MySection id="expertise" class="px-0"> <Section6 /> </MySection>
        <MySection id="contact"> <Section7 /> </MySection>
      </div>
    </body>
  </div>
</template>

<script setup lang="ts">
const navItems = [
  { id: "landing", title: "" },
  { id: "about", title: "Section 1" },
  { id: "avantages", title: "Section 2" },
  { id: "clients", title: "Section 3" },
  { id: "methode", title: "Section 4" },
  { id: "expertise", title: "Section 5" },
  { id: "contact", title: "Section 6" },
];

const currentSection = ref(0);

onMounted(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.intersectionRatio > 0) {
          const parent = entry.target.parentElement;
          const id = parent?.id;
          // if (!parent?.classList.contains("display"))
          //   parent?.classList.add("display");
          // console.log("get parent id ", entry.target.parentElement);
          currentSection.value = navItems.findIndex((nav) => nav.id === id);
        }
      });
    },
    {
      root: null,
      rootMargin: "0px",
      threshold: 1,
    }
  );
  // console.log(document.querySelectorAll("section .intersector"));
  document.querySelectorAll("section .intersector").forEach((section) => {
    observer.observe(section);
  });
});
</script>

<style scoped></style>
