<template>
  <ClientOnly>
    <Teleport to="#header">
      <div
        class="fixed z-50 top-0 p-0 w-full h-16 text-dark bg-light shadow-sm flex justify-center transition-all"
        ref="header"
      >
        <nav
          class="relative flex justify-center md:justify-between items-center max-w-7xl w-full h-full px-5 md:px-0 bg-light transition-all"
        >
          <button
            id="toggleMenu"
            class="absolute left-5 md:hidden"
            @click="toggleMenu"
          >
            <Icon name="material-symbols:menu" />
          </button>

          <button class="h-full" @click="smoothScroll(0)">
            <img
              class="h-full object-contain mix-blend-multiply"
              src="https://static.vecteezy.com/ti/vecteur-libre/p1/2228882-immobilier-logo-design-entreprise-signe-logo-vecteur-gratuit-vectoriel.jpg"
              alt=""
            />
          </button>

          <div class="flex justify-center items-stretch h-full">
            <ul class="nav-items" :class="{ '-translate-y-full': hideMenu }">
              <li
                v-for="(item, ind) in navItems"
                @click="goToSection(ind)"
                class="nav-item"
                :class="{ active: isActive(ind), hidden: ind == 0 }"
                :key="item.id + '-' + ind"
              >
                {{ item.title }}
              </li>
            </ul>
          </div>
        </nav>
      </div>
    </Teleport>
  </ClientOnly>
</template>

<script setup lang="ts">
const props = defineProps<{
  navItems: Array<{ id: string; title: string }>;
  activeSection: number;
}>();
const { navItems } = props;
const { activeSection } = toRefs(props);

const header = ref(null);

function goToSection(ind: number) {
  // setActive(ind);
  smoothScroll(document.getElementById(navItems[ind]?.id)?.offsetTop ?? 0);
}

function smoothScroll(to: number) {
  if (!hideMenu.value) toggleMenu();
  window.scrollTo({
    top: to,
    left: 0,
    behavior: "smooth",
  });
}

function isActive(index: number) {
  return index == activeSection.value;
}

const hideMenu = ref(true);

function toggleMenu() {
  hideMenu.value = !hideMenu.value;
}

onClickOutside(header, () => {
  if (!hideMenu.value) toggleMenu();
});
</script>

<style scoped>
.nav-items {
  @apply absolute 
  flex flex-col items-center w-full left-0 top-full -z-10 
  md:static md:flex-row md:transform-none md:w-fit md:z-10 
  bg-secondary text-primary md:bg-transparent md:text-secondary 
  transition-all md:transition-none;
}

.nav-item {
  @apply relative w-full h-full py-7 flex justify-center items-center transition-all text-light
  md:text-dark md:w-fit md:px-5 md:py-3
  hover:bg-primary/70 hover:cursor-pointer;
}

.nav-item.active {
  @apply before:absolute before:block before:w-full before:h-1 
          before:bg-primary before:top-0 before:left-0;
}

.hidden {
  display: none;
  background: transparent;
  padding: 0;
}
</style>
