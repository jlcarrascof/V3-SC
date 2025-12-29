<script setup lang="ts">
// Application logic goes here
import { ref } from 'vue'
const greeting = ref('Hello, EDTeam')
</script>

<template>
  <!-- HTML goes here -->
  <div>
    {{ greeting }}
  </div>
</template>

<style scoped></style>
