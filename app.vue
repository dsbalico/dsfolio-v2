<template>
    <NuxtLayout>
        <NuxtPage />
    </NuxtLayout>
</template>

<script setup lang="ts">
import content from '~/static/content.json';

useSeoMeta({
    keywords: content.meta.keywords,
})
</script>