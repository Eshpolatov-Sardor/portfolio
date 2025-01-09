<script setup>
useHead({
  title: 'MY Profile',
  link: [
    {
      rel: 'icon', type: 'image/png', href: '/people.png',
    },
  ],
})
</script>

<template>
  <div>
    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout>
  </div>
</template>

<style>
html, body , #__nuxt{
  height: 100vh;
  margin: 0;
  padding: 0;
}

html.dark {
  background: black;
  color: white;
}
</style>
