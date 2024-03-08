<script setup>

const { slug } = useRoute().params
</script>
<template>

    <article class="bg-white rounded-2xl p-2">
        <ContentDoc :path="`/posts/${slug}`" v-slot="{ doc }">

            <header>
                <div class="text-center p-5">
                    <h1 class="text-4xl font-semibold">{{ doc.title }}</h1>
                    <div class="text-gray-500 text-sm mt-4">{{ doc.date }}</div>
                </div>
                <div v-if="doc.tags" class="flex justify-center text-sm space-x-3 opacity-80">
                    <p v-for="tag in doc.tags" class="bg-gray-200 p-1 rounded-md">{{ tag }}</p>
                </div>
                <img :src="doc.thumbnail" class="w-1/2 mx-auto h-full object-cover " alt="">
            </header>

            <div class="mt-4 p-5 gap-5">
                <ContentRenderer :value="doc"></ContentRenderer>
            </div>
        </ContentDoc>
    </article>
</template>