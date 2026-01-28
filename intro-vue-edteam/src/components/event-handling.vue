<script setup lang="ts">
    import { computed, onMounted, onUnmounted, reactive } from 'vue';

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

    onMounted(() => {
        console.log('Working from the beginning')
        cart.items = [
            {
                id: 1,
                name: 'Basic',
                price: 20,
            },
            {
                id: 2,
                name: 'Medium',
                price: 30,
            },            {
                id: 3,
                name: 'Pro',
                price: 40,
            },            
        ]; 
    })

    onUnmounted(() => {
        console.log('Goodbye')
    }) 

    const cart = reactive<Cart>({
        category: 'hosting',
        description: 'EDTeam shopping cart',
        currency: 'USD',
        items: [] 
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