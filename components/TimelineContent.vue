<template>
    <div style="display: flex; gap: 12px;">
        <div style="width: 50px;">
            <img style="border-radius: 100%; width: 100%;" :src="props.image" />
        </div>
        <div style="align-self: center; width: 100%;">
            <a-typography-text strong>{{ props.organization }}</a-typography-text>

            <br />

            <div style="display: flex; justify-content: space-between;">
                <a-typography-text style="width: 60%;">{{ props.subtitle }}</a-typography-text>
                <a-typography-text style="color: gray; font-size: 12px; width: 40%;" align="right">{{ props.date }}</a-typography-text>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
const props = defineProps<{
    organization: string;
    subtitle: string;
    image: string;
    date: string;
}>();
</script>