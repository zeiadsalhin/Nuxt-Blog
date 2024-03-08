<script setup>
</script>
<template>

    <div>
        <ContentList path="/posts" :query="{ draft: false, sort: [{ date: -1 }] }" v-slot="{ list }">
            <div v-for="post in list" :key="post._path" class="blog-card bg-white rounded-xl overflow-hidden mb-4">
                <div class="h-[300px] relative mt-4">
                    <img :src="post.thumbnail" class="w-11/12 mx-auto h-full object-cover rounded-lg" alt="">
                </div>
                <div class="blog-card p-5">
                    <nuxt-link :to="`/${post.slug}`">
                        <h3 class="text-2xl font-semibold">{{ post.title }}</h3>
                    </nuxt-link>
                    <div class="date opacity-50">
                        {{ post.date }}
                    </div>
                    <div v-if="post.tags" class="flex space-x-3 text-sm opacity-80">
                        <p v-for="tag in post.tags" class="bg-gray-200 p-1 rounded-md">{{ tag }}</p>
                    </div>
                    <p class="p-2">{{ post.description.slice(0, 200) + "...." }}</p>
                </div>
            </div>
        </ContentList>
    </div>

</template>
<style>
/* body {
    @apply bg-zinc-200;
} */
</style>