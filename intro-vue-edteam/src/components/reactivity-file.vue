<script setup lang="ts">
    import { reactive, ref } from 'vue';

    const message = ref('Hi, EDTeam')
    const isVisible = ref(true)
    const total = ref(100)

    const user = ref({
        firstName: 'Juan',
        lastName: 'Perez',
        age: 18,        
    })

    const user = reactive({
        firstName: 'Juan',
        lastName: 'Perez',
        age: 18,
    })
</script>

<template>
    <div>
        <input type="text" v-model="message" />
        {{ message }}
    </div>
</template>

<style scoped>

</style>