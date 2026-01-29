<script setup lang="ts">
    import { ref, watch } from 'vue';

    const message = ref<string>(`Hi, EDTeam`)
    const error = ref<string>('')

    watch(message, (m) => {
        if (!m) {
            error.value = 'This field is required!!'
        } else {
            error.value = ''
        }       
    })
</script>

<template>
    <div class="flex">
        <div>Message: {{ message }} </div>
        <input v-model="message" type="text" />
        <span v-if="error" style="color: red">{{ error }}</span>
    </div>
</template>

<style scoped>
    .flex {
        display: flex;
        flex-direction: column;
        gap: 2px;
    }
</style>