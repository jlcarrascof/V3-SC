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

    const quantity = computed(() => cart.items.length)
</script>

<template>
    <div>
        {{ message }}
    </div>
    <div>
        Total Price: {{ totalPrice }} {{ cart.currency }}
    </div>
    <div>
        Total Quantity: {{ quantity }}
    </div>
</template>

<style scoped>

</style>