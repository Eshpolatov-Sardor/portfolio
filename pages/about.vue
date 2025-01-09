<script setup lang="ts">
import { onMounted, ref, computed } from "vue";
import { useI18n } from "vue-i18n";

useHead({
  title: 'MY About',
})


const { t } = useI18n();
const fullText = t("Read");

const textVisible = ref(false);
const displayedText = ref("");
const formattedText = computed(() =>
  displayedText.value.replace(/\n/g, "<br>")
);

function typeText() {
  let index = 0;
  const interval = setInterval(() => {
    if (index < fullText.length) {
      displayedText.value += fullText[index];
      index++;
    } else {
      clearInterval(interval);
    }
  }, 30);
}

onMounted(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      if (entries[0].isIntersecting) {
        textVisible.value = true;
        typeText();
        observer.disconnect();
      }
    },
    { threshold: 0.1 }
  );

  const textElement = document.querySelector(".typing-text");
  if (textElement) {
    observer.observe(textElement);
  }
});
</script>

<template>
  <div>
    <div
      class="flex flex-col md:flex-row justify-between items-center h-auto md:h-[82vh]"
    >
      <div class="relative w-full md:w-1/3">
        <div
          class="absolute w-[300px] h-[350px] sm:w-[350px] sm:h-[400px] md:w-[390px] md:h-[440px] mt-8 ml-12 md:ml-0 bg-gradient-to-t from-black to-yellow-400 rounded-lg dark:bg-gradient-to-t dark:to-blue-600"
        ></div>
        <NuxtImg
          class="w-[300px] sm:w-[350px] md:w-[390px] mt-20 md:mt-22 relative z-10 mx-auto md:mr-24 rounded-lg"
          src="/people_about.png"
        />
      </div>
      <div class="w-full md:w-2/3 mt-8 md:mt-0 text-center md:text-left">
        <h1
          class="text-2xl md:text-3xl text-blue-800 flex gap-4 items-center justify-center md:justify-start"
        >
          <NuxtImg class="w-6" src="/right.png" /> {{ $t("About") }}
        </h1>
        <p
          class="typing-text text-sm md:text-base leading-6 opacity-50 h-auto md:h-[250px] overflow-hidden px-4 md:px-0"
          :class="{ show: textVisible }"
          v-html="formattedText"
        ></p>
        <NuxtLink to="skills">
          <button class="bg-blue-800 text-white py-2 px-4 mt-8 rounded-lg">
            {{ $t("Skills") }}
          </button>
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<style scoped>
.typing-text {
  white-space: pre-wrap;
  opacity: 0;
  transition: opacity 0.5s;
}

.typing-text.show {
  opacity: 1;
}
</style>
