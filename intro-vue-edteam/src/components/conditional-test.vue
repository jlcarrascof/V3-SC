<script setup lang="ts">
    import { ref } from 'vue';

    const text = ref<string>("Hello, EDTeam")
    const isVisible = ref<boolean>(true)
    const age = ref<number>(15)
    const description = ref<string>("")
</script>

<template>
    <input v-model="description" />
    <div v-if="isVisible">
        {{ text }}
    </div>
    <div v-else-if="age > 18">
        Hello from the second block!!
        <br />
        <span v-show="description.length > 0">{{ description }}</span>
    </div>
    <div v-else>
        <span>Alternative Text</span>
    </div>
</template>

<style scoped>

</style>