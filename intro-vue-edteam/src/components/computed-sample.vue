<script setup lang="ts">
import { reactive } from 'vue';

    const cart = reactive({
        category: 'hosting',
        description: 'EDTeam shopping cart',
        currency: 'USD',
        items: [
            {
                id: 1,
                description: 'Basic',
                price: 20,
            },
            {
                id: 2,
                description: 'Medium',
                price: 30,
            },            {
                id: 3,
                description: 'Pro',
                price: 40,
            },            
        ]
    })
</script>

<template>
    <div>
        {{ cart.description }}
    </div>
</template>

<style scoped>

</style>