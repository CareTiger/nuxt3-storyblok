<template>
    <div>
        <div v-html="resolvedRichText" class="prose"></div>
    </div>
</template>
<script setup>
const route = useRoute();
const storyblokApi = useStoryblokApi();
const { data } = await storyblokApi.get('cdn/stories', {
    starts_with: 'articles' + '/' + route.params.slug[0],
});
// const { data } = await storyblokApi.get('cdn/stories', {
//     starts_with: 'authors/',
//     // by_uuid: data.stories[0].content.author,
// });
// console.log(data.stories[0]);
console.log(data);
const resolvedRichText = computed(() =>
    renderRichText(data.stories[0].content.body)
);
</script>
