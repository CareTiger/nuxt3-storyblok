<template>
    <div class="grid sm:grid-cols-3 gap-5">
        <div v-for="article in data.stories">
            <ArticleCard :article="article" :slug="article.slug" />
        </div>
    </div>
</template>

<script setup>
const storyblokApi = useStoryblokApi();
const { data } = await storyblokApi.get('cdn/stories', {
    starts_with: 'articles',
});
</script>
