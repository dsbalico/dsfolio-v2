<template>
    <div class="drawer-nav">
        <a-typography-title style="font-weight: bold; margin: 0;" :level="4">
            <span style="color: #1677FF">DS</span>Folio
        </a-typography-title>

        <div class="nav-links">
            <NuxtLink to="/">
                <a-button v-bind:class="{ 'active': current === 'index' }" type="text">
                    <home-outlined />
                    Home
                </a-button>
            </NuxtLink>
            <NuxtLink to="/about">
                <a-button v-bind:class="{ 'active': current === 'about' }" type="text">
                    <user-outlined />
                    About
                </a-button>
            </NuxtLink>
            <NuxtLink to="/projects">
                <a-button v-bind:class="{ 'active': current === 'projects' }" type="text">
                    <book-outlined />
                    Projects
                </a-button>
            </NuxtLink>
            <NuxtLink to="/contact">
                <a-button v-bind:class="{ 'active': current === 'contact' }" type="text">
                    <mail-outlined />
                    Contact
                </a-button>
            </NuxtLink>
        </div>
        <a-button type="text" class="hamburger" @click="showDrawer" style="margin-left: 20px;">
            <MenuOutlined />
        </a-button>
    </div>

    <!-- Drawer -->
    <a-drawer placement="left" :closable="false" :open="open" @close="onClose">
        <template #title>
            <a-typography-title style="font-weight: bold; margin: 0;" :level="4">
                <span style="color: #1677FF">DS</span>Folio
            </a-typography-title>
        </template>

        <template #extra>
            <a-button type="text" ghost @click="onClose"><CloseOutlined /></a-button>
        </template>

        <div class="drawer-nav-links">
            <NuxtLink to="/" @click="onClose">
                <a-button v-bind:class="{ 'active': current === 'index' }" type="text">
                    <home-outlined />
                    Home
                </a-button>
            </NuxtLink>
            <NuxtLink to="/about" @click="onClose">
                <a-button v-bind:class="{ 'active': current === 'about' }" type="text">
                    <user-outlined />
                    About
                </a-button>
            </NuxtLink>
            <NuxtLink to="/projects" @click="onClose">
                <a-button v-bind:class="{ 'active': current === 'projects' }" type="text">
                    <book-outlined />
                    Projects
                </a-button>
            </NuxtLink>
            <NuxtLink to="/contact" @click="onClose">
                <a-button v-bind:class="{ 'active': current === 'contact' }" type="text">
                    <mail-outlined />
                    Contact
                </a-button>
            </NuxtLink>
        </div>
    </a-drawer>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import { useRoute } from 'vue-router';

export default defineComponent({
    setup() {
        const open = ref<boolean>(false);
        const route = useRoute();
        const current = ref<string>(route.name as string);

        function showDrawer(): void { open.value = true; };

        function onClose(): void { open.value = false; };

        watchEffect(() => {
            current.value = route.name as string;
        });

        return {
            open,
            showDrawer,
            current,
            onClose,
        };
    },
});
</script>

<style scoped>
.drawer-nav {
    display: flex;
    justify-content: space-between;
    border-bottom: solid 1px #f0f0f0;
    padding: 14px;
}

.hamburger {
    display: block;
}

.nav-links {
    display: none;
}

.drawer-nav-links {
    display: flex;
    flex-direction: column;
    gap: 10px;
    margin-top: 20px;
}

.drawer-nav-links .ant-btn {
    width: 100%;
    text-align: left
}

.active {
    background-color: #1677FF;
    color: white;
}

.drawer-nav-links .ant-btn:hover, .nav-links .ant-btn:hover {
    color: white;
    background-color: #1677FF;
}

/* lg */
@media (min-width: 768px) {
    .hamburger {
        display: none;
    }

    .nav-links {
        display: flex;
        gap: 8px;
    }

    .drawer-nav {
        padding: 14px 32px;
    }
}
</style>