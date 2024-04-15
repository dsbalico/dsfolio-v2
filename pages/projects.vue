<template>
    <div class="content-full">
        <div>
            <a-typography-title align="center" :level="1" style="font-weight: bold;">
                My Projects
            </a-typography-title>

            <a-row style="margin: 32px 0 24px 0;" type="flex" justify="center" :gutter="[16, 16]">
                <Project 
                    v-for="(project, index) in content.projects"
                    :key="index"
                    :title="project.title"
                    :description="project.description"
                    :skills="project.skills"
                    :link="project.link"
                    :github="project.github" />
            </a-row>

            <a-divider></a-divider>

            <div style="width: 100%; text-align: center;">
                <NuxtLink :to="content.social_links.github">
                    <a-button type="primary">
                        See More at Github
                    </a-button>
                </NuxtLink>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
import content from '~/static/content.json';

useHead({
    title: "Projects",
})
</script>

<style scoped></style>