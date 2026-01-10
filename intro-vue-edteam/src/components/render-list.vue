<script setup lang="ts">
    import { ref } from 'vue';

    const names = ref<string[]>([])
</script>

<template>
    <div>
        <ul>
            <li v-for="name in names" :key="name">
                {{ name }}
            </li>
        </ul>
    </div>
</template>

<style scoped>

</style>