<script setup lang="ts">
</script>

<template>
  <div class="md:h-[458px]">
    <div
      class="grid grid-cols-1 md:grid-cols-2 gap-4 p-4 w-[360px] md:w-full mt-28"
    >
      <div>
        <h1 class="text-3xl text-blue-800">{{ $t("Hello") }}</h1>
        <h1 class="text-4xl font-bold py-4">{{ $t("Name") }}</h1>
        <p class="text-xl leading-8 opacity-50 md:w-[550px] w-96">
          {{ $t("Profession") }}
        </p>
        <NuxtLink to="contact">
          <button class="bg-blue-800 text-white py-2 px-4 mt-8 rounded-lg">
            {{ $t("Contact") }}
          </button>
        </NuxtLink>
      </div>
      <div class="relative">
        <div
          class="absolute w-[370px] h-[325px] sm:w-[350px] sm:h-[350px] md:w-[390px] md:h-[385px] md:ml-6 bg-gradient-to-t from-black to-yellow-400 rounded-lg dark:bg-gradient-to-t dark:to-blue-600"
        ></div>
        <NuxtImg
          class="w-[390px] sm:w-[350px] md:w-[390px] relative z-10 ml-6 sm:mr-16 md:mr-24"
          src="/people.png"
        />
      </div>
    </div>
  </div>
</template>
