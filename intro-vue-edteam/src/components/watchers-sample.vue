<script setup lang="ts">
    import { ref } from 'vue';

    const message = ref<string>(`Hi, EDTeam`)
    const error = ref<string>('')
</script>

<template>
    <div>
        <div>Message: {{ message }}</div>
        <input v-model="message" type="text" />
        <span style="color: red">{{ error }}</span>
    </div>
</template>

<style scoped>

</style>