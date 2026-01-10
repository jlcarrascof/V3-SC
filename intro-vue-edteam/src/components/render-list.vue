<script setup lang="ts">
    import { ref } from 'vue';

    interface User {
        id: number,
        firstName: string,
        secondName: string,
        age: number
    }

    const names = ref<string[]>([
        'John', 'Juan', 'Jose', 'Christian', 'Carlos'
    ])

    const users = ref<User[]>([{
        id: 1,
        firstName: 'John',
        secondName: 'Doe',
        age: 30
    }, {
        id: 2,
        firstName: 'Jane',
        secondName: 'Smith',
        age: 25 
    }, {
        id: 3,
        firstName: 'Mike',
        secondName: 'Johnson',
        age: 40
    }, {
        id: 4,
        firstName: 'Emily',
        secondName: 'Davis',
        age: 35        
    }, {
        id: 5,
        firstName: 'David',
        secondName: 'Wilson',
        age: 28
    }]);
</script>

<template>
    <div>
        <h2>Names</h2>
        <ul>
            <li v-for="name in names" :key="name">
                {{ name }}
            </li>
        </ul>
    </div>
</template>

<style scoped>

</style>