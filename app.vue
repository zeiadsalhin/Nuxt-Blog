<script setup lang="ts">
useSeoMeta({
  title: 'Nuxt3 Blog',
  ogTitle: 'Nuxt JS Blog',
  description: 'CMS Blog created with Nuxt 3',
  ogDescription: 'My CMS Blog created with Nuxt 3',
  ogImage: 'https://courses.pactel.info/logo_test.svg',
  twitterCard: 'summary_large_image',
})
</script>
<template>
  <div class="max-w-3xl px-4 mx-auto">

    <header class=" mb-4 flex justify-between items-end ">
      <div class="mt-8">
        <h1 class="text-2xl font-semibold"><nuxt-link to="/">Blog</nuxt-link></h1>
        <p class="text-gray-800">Nuxt programming</p>
      </div>
      <Btn><a href="https://github.com/zeiadsalhin">Contact Me</a></Btn>
    </header>

    <!--Content-->

    <NuxtPage />

  </div>
</template>
