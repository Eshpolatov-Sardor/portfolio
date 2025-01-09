<script setup lang="ts">
import { ref, onMounted, onUnmounted, nextTick } from "vue";
import { useI18n } from "vue-i18n";


useHead({
  title: 'MY Skills',
})


const { t } = useI18n();
const skillButtons = ref<HTMLElement[]>([]);
const currentIndex = ref(0);
const skillImage = ref<string>(""); 
const skillImageContainer = ref<HTMLElement | null>(null);
let animationTimeout: any = null;

interface SkillIcons {
  html: string;
  css: string;
  tailwind: string;
  pug: string;
  sass: string;
  bootstrap: string;
  javascript: string;
  typescript: string;
  vue: string;
  nuxt: string;
  vee: string;
  pinia: string;
  git: string;
  github: string;
}

const skills = [
  "html",
  "css",
  "tailwind",
  "bootstrap",
  "javascript",
  "typescript",
  "vue",
  "nuxt",
  "vee",
  "pinia",
  "git",
  "github",
];
const skillIcons: SkillIcons = {
  html: "/html.png",
  css: "/css.png",
  tailwind: "/tailwind.png",
  bootstrap: "/bootstrap.png",
  javascript: "/javascript.png",
  typescript: "/typescript.png",
  vue: "/vue.png",
  nuxt: "/nuxt.png",
  vee: "/vee.png",
  pinia: "/pinia.png",
  git: "/git.png",
  github: "/github.png",
};

function showNextSkill() {
  if (currentIndex.value < skillButtons.value.length) {
    const currentButton = skillButtons.value[currentIndex.value];
    const skillName = skills[currentIndex.value];

    skillImage.value = "";

    nextTick(() => {
      if (skillImageContainer.value) {
        skillImage.value = skillIcons[skillName];

        currentButton.style.display = "inline-block";
        currentIndex.value++;

        animationTimeout = setTimeout(showNextSkill, 1000);
      }
    });
  }
}

onMounted(() => {
  skillButtons.value = Array.from(
    document.querySelectorAll(".skill-button")
  ) as HTMLElement[];
  skillImageContainer.value = document.querySelector(
    ".skill-image-container"
  ) as HTMLElement;
  showNextSkill();
});

onUnmounted(() => {
  clearTimeout(animationTimeout);
});
</script>

<template>
  <div>
    <div
      class="flex flex-col md:flex-row justify-between items-center h-auto md:h-[82vh] px-2"
    >
      <div class="relative w-full md:w-1/3 mb-6 md:mb-0">
        <div
          class="absolute w-[385px] h-[500px] md:w-[390px] md:h-[520px] mt-4 md:mt-0 bg-gradient-to-t from-black to-yellow-400 rounded-lg dark:bg-gradient-to-t dark:to-blue-600"
        ></div>
        <NuxtImg
          class="w-[390px] relative z-10 mr-24"
          src="/people_skills.png"
        />
        <div class="skill-image-container">
          <NuxtImg class="skill-image" :src="skillImage" alt="Skill Icon" />
        </div>
      </div>
      <div class="w-full md:w-2/3">
        <h1 class="text-3xl text-blue-800 flex gap-4 items-center">
          <NuxtImg class="w-6" src="/right.png" />
          {{ $t("Skills") }}
        </h1>
        <ol class="grid md:grid-cols-6 grid-cols-3 gap-2 mt-4">
          <li v-for="skill in skills" :key="skill">
            <button
              class="skill-button border py-2 px-4 w-32 rounded-lg hover:bg-blue-600 mt-1"
              :data-skill="skill"
              style="display: none"
            >
              {{ skill }}
            </button>
          </li>
        </ol>
        <NuxtLink to="/contact">
          <button class="bg-blue-800 text-white py-2 px-4 mt-8 rounded-lg">
            {{ $t("Contact") }}
          </button>
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<style scoped>
.skill-image-container {
  z-index: 1;
  pointer-events: none;
}

.skill-image {
  margin-top: 310px;
  margin-left: 270px;
  width: 100px;
  height: 100px;
  opacity: 0;
  z-index: 10;
  position: absolute;
  border-radius: 10px;
  top: 0;
  left: 0;
  animation: fadeInUp 0.5s ease forwards;
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@media (max-width: 768px) {
  .skill-image {
    margin-top: 310px;
    margin-left: 270px;
    width: 80px;
    height: 80px;
  }

  .skill-button {
  }

  .w-full {
    width: 100%;
  }
}
</style>

