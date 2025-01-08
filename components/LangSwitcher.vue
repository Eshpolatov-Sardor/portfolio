<script lang="ts" setup>
const { locale } = useI18n()
</script>

<template>
  <div>
    <form>
      <select v-model="locale" class="bg-transparent outline outline-1 rounded-md w-12 dark:text-white dark:bg-blue-500 flex items-center"> ">
        <option value="en">eng</option>
        <option value="ru">rus</option>
        <option value="uz">uzb</option>
      </select>
      <!-- <p>{{ $t('welcome') }}</p> -->
    </form>
  </div>
</template>

<style scoped></style>
