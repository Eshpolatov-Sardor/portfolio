<script lang="ts" setup>
import { ref } from "vue";
const isOpen = ref(false);
const istoggleMenu = ref(true);

function toggleMenu() {
  isOpen.value = !isOpen.value;
  istoggleMenu.value = !istoggleMenu.value;
}
function nullMenu() {
  isOpen.value = false;
    istoggleMenu.value = true;
}
</script>
<template>
  <nav class="">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16">
        <div class="-mr-2 flex md:hidden items-center gap-2">
          <span>
            <DarkToggle />
          </span>
          <div >
            <button
              @click="toggleMenu" v-if="istoggleMenu"
              class="p-2 rounded-md text-gray-400 hover:text-white focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-gray-800 focus:ring-white"
            >
              <NuxtImg class="h-6" src="/barmenu.png" alt="menu" />
            </button>
            <button
              @click="nullMenu" v-else-if="!istoggleMenu"
              class="p-2 rounded-md text-gray-400 hover:text-white focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-gray-800 focus:ring-white"
            >
              <NuxtImg class="h-6" src="/xmenu.png" alt="menu" />
            </button>
          </div>
        </div>
        <div v-if="isOpen">
          <ul
            class="mt-10 space-y-4 -ml-16 absolute z-40 dark:bg-gray-800 bg-blue-600 p-4 rounded-lg"
          >
            <li>
              <NuxtLink to="/" class="text-white hover:underline">{{
                $t("Home")
              }}</NuxtLink>
            </li>
            <li>
              <NuxtLink to="/about" class="text-white hover:underline">{{
                $t("About")
              }}</NuxtLink>
            </li>
            <li>
              <NuxtLink to="/skills" class="text-white hover:underline">{{
                $t("Skills")
              }}</NuxtLink>
            </li>
            <li>
              <NuxtLink to="/contact" class="text-white hover:underline">{{
                $t("Contact")
              }}</NuxtLink>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </nav>
</template>