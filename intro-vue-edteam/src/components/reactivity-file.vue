<script setup lang="ts">
    import { reactive, ref } from 'vue';

    const message = ref<string>('Hi, EDTeam')
    const isVisible = ref<boolean>(true)
    const total = ref<number>(100)

/*  const user = ref({
        firstName: 'Juan',
        lastName: 'Perez',
        age: 18,        
    })
 */

 
    const user = reactive({
        firstName: 'Juan',
        lastName: 'Perez',
        age: 18,
    })

    const updating = () => {
        console.log(user.firstName)
        console.log(message.value)
    }
</script>

<template>
    <div>
        <input type="text" v-model="message" />
        {{ message }}
        {{ user.firstName }}
    </div>
</template>

<style scoped>

</style>