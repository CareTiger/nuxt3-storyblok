<template>
    <div v-editable="blok">
        <StoryblokComponent v-for="component in blok.body" :key="component._uid" :blok="component" />
    </div>
</template>
<script setup>
defineProps({
    blok: {
        type: Object,
        required: true
    }
})
</script>