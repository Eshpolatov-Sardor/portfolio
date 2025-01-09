<script lang="ts" setup>
</script>
<template>
  <div
    class="flex flex-wrap justify-center items-center gap-12 h-[82vh] p-6 dark:text-white"
  >
    <div>
      <h1 class="text-4xl font-bold">{{ $t("Contact") }}</h1>
      <p class="text-lg">
        {{ $t("Youcan") }}
      </p>
    </div>
    <ul class="space-y-4 text-lg">
      <li>
        <a href="tel:+998901234567" class="hover:underline">
          {{ $t("Phone") }}
        </a>
      </li>
      <li>
        <a href="mailto:eshpolatovsardor@gmail.com" class="hover:underline">
          {{ $t("Email") }}
        </a>
      </li>
      <li>
        <a
          href="https://github.com/Eshpolatov-Sardor"
          target="_blank"
          class="hover:underline"
        >
          {{ $t("GitHub") }}
        </a>
      </li>
      <li>
        <a
          href="https://t.me/sirojiddinvich_04"
          target="_blank"
          class="hover:underline"
        >
          {{ $t("Telegram") }}
        </a>
      </li>
      <li>
        <a
          href="https://instagram.com/sardor_079_04"
          target="_blank"
          class="hover:underline"
        >
          {{ $t("Instagram") }}
        </a>
      </li>
    </ul>
  </div>
</template>
  
<style scoped>
a {
  transition: color 0.3s ease;
}

a:hover {
  color: #2b6cb0;
}
</style>
