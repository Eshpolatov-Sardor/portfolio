<template>
  <nav class="bg-blue-500 p-2 flex justify-between items-center">
    <div class="text-white text-lg">
      <NuxtImg class="h-12" src="/logo.png" alt="lion Logo" />
    </div>
    <ul class="flex space-x-4 gap-4 px-4 ">
      <li>
        <NuxtLink to="/" class="text-white hover:underline">{{ $t('Home') }}</NuxtLink>
      </li>
      <li>
        <NuxtLink to="/about" class="text-white hover:underline">{{ $t('About') }}</NuxtLink>
      </li>
      <li>
        <NuxtLink to="/skills" class="text-white hover:underline">{{ $t('Skills') }}</NuxtLink>
      </li>
      <li>
        <NuxtLink to="/text" class="text-white hover:underline">{{ $t('Contact') }}</NuxtLink>
      </li>
      <li>
        <DarkToggle />
      </li>
      <li>
        <LangSwitcher />
      </li>
    </ul>
    <BarMenu class="md:hidden" />
  </nav>
</template>

<script setup lang="ts">
</script>

<style scoped>
@media screen and (max-width: 768px) {
  nav {
    align-items: center;
  }
  .space-x-4{
    display: none;
  }
  
}
</style>
