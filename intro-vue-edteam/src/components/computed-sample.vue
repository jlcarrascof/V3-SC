<script setup lang="ts">
import { computed, reactive } from 'vue';

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

    const message = computed(() => {
        return cart.description
    })

    const totalPrice = computed(() => {
        return cart.items.reduce((accumulator, current) => 
            accumulator + current.price, 0)
    })
</script>

<template>
    <div>
        {{ cart.description }}
    </div>
</template>

<style scoped>

</style>