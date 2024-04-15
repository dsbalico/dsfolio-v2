<template>
    <div class="content-vh">
        <div class="content">
            <a-typography-title style="font-weight: bold; font-size: 40px;">
                Let's Get in Touch:
                <span style="color: #1677FF;">Ways to Connect with Me</span>
            </a-typography-title>
            <a-typography-paragraph>
                Thank you for your interest in getting in touch with me. I welcome your feedback,
                questions, and suggestions. If you have a specific question or comment, please feel free to email me
                directly at <span style="color: #1677FF">{{ content.email }}</span> I make an effort to respond to all messages within 24 hours,
                although it may take me longer during busy periods. Finally, if you prefer to connect on social media,
                you can connect with me using the social media links below.
            </a-typography-paragraph>

            <a :href="content.social_links.facebook" target="_blank">
                <a-button type="text">
                    <facebook-outlined /> Follow on Facebook
                </a-button>
            </a>

            <br />

            <a :href="content.social_links.instagram" target="_blank">
                <a-button type="text">
                    <instagram-outlined /> Follow on Instagram
                </a-button>
            </a>

            <br />

            <a :href="content.social_links.twitter" target="_blank">
                <a-button type="text">
                    <twitter-outlined /> Follow on Twitter
                </a-button>
            </a>

            <br />

            <a :href="content.social_links.linkedin" target="_blank">
                <a-button type="text">
                    <linkedin-outlined /> Follow on Linkedin
                </a-button>
            </a>

            <a-divider></a-divider>

            <a :href="'mailto:' + content.email">
                <a-button type="text">
                    <mail-outlined /> danielshan.balico@gmail.com
                </a-button>
            </a>
        </div>
    </div>
</template>

<script setup lang="ts">
import content from '~/static/content.json';

useHead({
    title: "Contact",
})
</script>

<style scoped>
.ant-typography {
    font-size: 16px;
}

.ant-btn {
    font-size: 16px;
}

.anticon {
    color: #1677FF;
}

.content {
    width: 100%;
}

/* lg */
@media (min-width: 1024px) {
    .content {
        width: 80%;
    }
}
</style>