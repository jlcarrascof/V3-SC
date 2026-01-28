<script setup lang="ts">
    import { computed, onMounted, reactive } from 'vue';

    interface Cart {
        category: string,
        description: string,
        currency: string,
        items: Item[]
    }

    interface Item {
        id: number,
        name: string,
        price: number        
    }

    onMounted
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

    const message = computed({
        get() {
            return cart.description
        },
        set(newVal) {
            cart.description = newVal
        }
    })

    const totalPrice = computed(() => {
        return cart.items.reduce((accumulator, current) => 
            accumulator + current.price, 0)
    })

    const quantity = computed(() => cart.items.length)

    const inputHandler = () => {
        console.log(cart.description)
    }
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
    <input v-model="cart.description" type="text" @keyup.enter="inputHandler" />
    <button @click="message='Hi, from the Vue 3 course'">Update Description</button>
</template>

<style scoped>

</style>