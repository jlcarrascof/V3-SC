<script setup lang="ts">
    import { ref } from 'vue';

    const text = ref<string>("Hello, EDTeam")
    const isVisible = ref<boolean>(true)


</script>

<template>
    <div v-if="isVisible">
        {{ text }}
    </div>
</template>

<style scoped>

</style>