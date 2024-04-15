<template>
    <a-col>
        <a-card :title="props.title">
            <template #extra>
                <a :href="github" target="_blank"><github-outlined /></a>
                <a :href="link" target="_blank" style="margin-left: 10px;"><global-outlined /></a>
            </template>

            <p style="margin-bottom: 16px;">
                {{ props.description }}
            </p>

            <template v-for="skill in props.skills">
                <a-tag color="blue">{{ skill }}</a-tag>
            </template>
        </a-card>
    </a-col>
</template>

<script setup lang="ts">
const props = defineProps<({
    title: string,
    description: string,
    skills: string[],
    link: string,
    github: string
})>();
</script>