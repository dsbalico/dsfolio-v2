<template>
    <div class="content-vh">
        <a-flex gap="50" horizontal justify="center" align="center">
            <div class="profile-info">
                <!-- Small screen profile image -->
                <img class="sm-profile-image" alt="Image of Daniel Shan Balico" width="85px" :src="content.index_image" />

                <!-- Info -->
                <a-typography-title :level="4" style="margin: 0">
                    {{ content.role }}
                </a-typography-title>
                <a-typography-title :level="1" style=" margin: 0 0 10px 0; font-weight: bold;">
                    {{ content.name }}
                </a-typography-title>
                <a-typography-paragraph align="justify" style="font-size: 16px; color: #71717a;">
                    {{ content.description }}
                </a-typography-paragraph>

                <!-- Buttons -->
                <a-flex gap="8" style="margin-top: 25px;">
                    <NuxtLink to="/projects">
                        <a-button type="primary">My Projects</a-button>
                    </NuxtLink>
                    <NuxtLink to="/about">
                        <a-button type="text">More About Me
                            <RightOutlined />
                        </a-button>
                    </NuxtLink>
                </a-flex>
            </div>

            <!-- Large screen profile image -->
            <div class="profile-image">
                <a-image style="border-radius: 15px;" :width="300" rotate="45"
                    :src="content.index_image" alt="Image of Daniel Shan Balico" />
            </div>
        </a-flex>
    </div>
</template>

<script setup lang="ts">
import content from '~/static/content.json';
</script>

<style scoped>
.profile-image {
    display: none;
    rotate: 4deg;
}

.sm-profile-image {
    border-radius: 100%;
    margin-bottom: 18px;
}

:deep(.ant-image-mask) {
    border-radius: 15px;
}

.content-vh {
    padding-top: 85px !important;
}

/* lg */
@media (min-width: 768px) {
    .profile-info {
        width: 60%;
    }

    .profile-image {
        display: block;
    }

    .sm-profile-image {
        display: none;
    }

    .content-vh {
        padding-top: 0 !important;
    }
}
</style>