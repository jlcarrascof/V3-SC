<script setup lang="ts">
    import { ref } from 'vue';

    const message = ref('Hi, EDTeam')
</script>

<template>
    <div>
        <input type="text" v-model="message" />
        {{ message }}
    </div>
</template>

<style scoped>

</style>