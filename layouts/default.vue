<template>
    <a-extract-style>
        <div class="container">
            <Navbar />
            <slot />
        </div>
    </a-extract-style>
</template>

<script setup lang="ts">
</script>

<style scoped>
.container {
    background-color: #fff;
}

/* lg */
@media (min-width: 1024px) {
    .container {
        width: 80%;
        margin: 0 auto;
    }
}
</style>