<script setup lang="ts">
    import { ref } from 'vue';

    interface User {
        id: number,
        firstName: string,
        lastName: string,
        age: number
    }

    const names = ref<string[]>([
        'John', 'Juan', 'Jose', 'Christian', 'Carlos'
    ])

    const users = ref<User[]>([{
        id: 1,
        firstName: 'John',
        lastName: 'Doe',
        age: 30
    }, {
        id: 2,
        firstName: 'Jane',
        lastName: 'Smith',
        age: 25 
    }, {
        id: 3,
        firstName: 'Mike',
        lastName: 'Johnson',
        age: 40
    }, {
        id: 4,
        firstName: 'Emily',
        lastName: 'Davis',
        age: 35        
    }, {
        id: 5,
        firstName: 'David',
        lastName: 'Wilson',
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
    <div>
        <h2>Users</h2>
        <ul>
            <li v-for="user in users" :key="user.id">
               {{ user.id }} {{ user.firstName }}  {{ user.lastName }} {{ user.age }}
            </li>
        </ul>
    </div>
</template>

<style scoped>

</style>