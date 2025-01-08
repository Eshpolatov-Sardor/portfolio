<template>
  <footer class="bg-blue-500 p-[2px] mt-[9px] flex justify-between items-center">
    <NuxtImg class="h-12" src="/logo.png" alt="lino Logo" />
    <p class="text-white text-sm">
      &copy; {{ new Date().getFullYear() }} - {{$t('Dasturchi')}}:
      <a href="https://t.me/sirojiddinvich_04" class="hover:underline"
        >Eshpo'latov Sardor</a
      >
    </p>
    <p class="w-12"></p>
  </footer>
</template>