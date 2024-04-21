<template>
    <div class="content-full">
        <a-typography-title align="center" style="font-weight: bold;">About Me</a-typography-title>

        <section class="first-section">
            <!-- Paragraph Section -->
            <div>
                <a-typography-paragraph align="justify">
                    {{ content.about_description }}
                </a-typography-paragraph>
                <a-typography-paragraph>
                    <span an style="font-weight: bold;">Programming Languages</span> <br />
                    <a-tag style="margin-top: 5px;" v-for="skill in content.skills.proglang" color="blue">{{ skill }}</a-tag>
                </a-typography-paragraph>
                <a-typography-paragraph>
                    <span an style="font-weight: bold;">Libraries & Frameworks</span> <br />
                    <a-tag style="margin-top: 5px;" v-for="skill in content.skills.libfw" color="blue">{{ skill }}</a-tag>
                </a-typography-paragraph>
                <a-typography-paragraph>
                    <span an style="font-weight: bold;">Tools & Platforms</span> <br />
                    <a-tag style="margin-top: 5px;" v-for="skill in content.skills.toolplat" color="blue">{{ skill }}</a-tag>
                </a-typography-paragraph>

                <a-divider style="margin: 0 0 15px 0;"></a-divider>

                <!-- Social Links -->
                <div class="social-links">
                    <NuxtLink :to="content.social_links.github">
                        <a-button type="text">
                            <github-outlined />
                        </a-button>
                    </NuxtLink>
                    <NuxtLink :to="content.social_links.twitter">
                        <a-button type="text">
                            <twitter-outlined />
                        </a-button>
                    </NuxtLink>
                    <NuxtLink :to="content.social_links.linkedin">
                        <a-button type="text">
                            <linkedin-outlined />
                        </a-button>
                    </NuxtLink>
                    <NuxtLink :to="content.social_links.facebook">
                        <a-button type="text">
                            <facebook-outlined />
                        </a-button>
                    </NuxtLink>
                    <NuxtLink :to="content.social_links.instagram">
                        <a-button type="text">
                            <instagram-outlined />
                        </a-button>
                    </NuxtLink>
                </div>
            </div>

            <!-- Image Section -->
            <div class="profile-image">
                <a-image style="border-radius: 15px;" rotate="45" :src="content.about_image" alt="Image of Daniel Shan Balico" />
            </div>
        </section>

        <!-- Education & Experience -->
        <section class="second-section">
            <!-- Education -->
            <a-card>
                <template #title>
                    <bank-outlined />
                    Education
                </template>

                <TimelineContent v-for="(edu, index) in content.education" :key="index" :organization="edu.organization"
                    :subtitle="edu.subtitle" :date="edu.date" :image="edu.image" />
            </a-card>

            <!-- Experience -->
            <a-card>
                <template #title>
                    <solution-outlined />
                    Experience
                </template>

                <TimelineContent v-for="(exp, index) in content.experience" :key="index"
                    :organization="exp.organization" :subtitle="exp.subtitle" :date="exp.date" :image="exp.image" />
            </a-card>
        </section>

        <!-- Certifications -->
        <a-card style="width: 100%; margin-top: 15px;">
            <template #title>
                <safety-certificate-outlined />
                Certifications
            </template>

            <a-image-preview-group>
                <a-carousel arrows>
                    <template #prevArrow>
                        <div class="custom-slick-arrow" style="left: 10px; z-index: 1">
                            <left-circle-outlined />
                        </div>
                    </template>
                    <template #nextArrow>
                        <div class="custom-slick-arrow" style="right: 10px">
                            <right-circle-outlined />
                        </div>
                    </template>

                    <a-image v-for="cert in content.certificates" :src="cert.image" :alt="cert.title" />
                </a-carousel>
            </a-image-preview-group>

            <a-divider></a-divider>
        </a-card>
    </div>
</template>

<script setup lang="ts">
import content from '~/static/content.json';

useHead({
    title: "About",
})
</script>

<style scoped>
.ant-carousel :deep(.slick-slide) {
    text-align: center;
    /* line-height: 160px; */
    background: #fff;
    overflow: hidden;
}

.ant-carousel :deep(.slick-arrow.custom-slick-arrow) {
    width: 25px;
    height: 25px;
    font-size: 25px;
    color: #1677FF;
    background-color: rgba(31, 45, 61, 0.11);
    opacity: 0.3;
    z-index: 1;
}

.ant-carousel :deep(.custom-slick-arrow:before) {
    display: none;
}

.ant-carousel :deep(.custom-slick-arrow:hover) {
    opacity: 0.5;
}

.first-section :deep(.ant-image-mask) {
    border-radius: 15px;
}

.profile-image {
    text-align: center;
    margin-top: 25px;
}

.ant-image-img {
    width: 100%;
}

.social-links {
    display: flex;
    gap: 8px;
    justify-content: center;
}

.social-links a button span {
    font-size: 20px;
    color: gray;
}

.second-section {
    margin-top: 32px;
}

.second-section>div:nth-child(2) {
    margin-top: 15px;
}

.ant-card-head-title span {
    margin-right: 4px;
    color: #1677FF;
}

/* lg */
@media (min-width: 1024px) {
    .first-section {
        display: flex;
        gap: 32px;
        justify-content: center;
    }

    :deep(.ant-image-img) {
        width: 250px !important;
    }

    .social-links {
        justify-content: flex-start;
    }

    .profile-image {
        margin-top: 0px;
    }

    .second-section {
        display: flex;
        flex-wrap: nowrap;
        gap: 20px;
        justify-content: center;
    }

    .second-section>div:nth-child(2) {
        margin-top: 0px;
    }
}

.ant-card {
    width: 100% !important;
}

.ant-card-body>div:nth-child(n + 2) {
    margin-top: 12px;
}
</style>