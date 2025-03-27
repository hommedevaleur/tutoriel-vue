<template>
    <div>
        <h1>{{ message }}</h1>
        <p>Ceci est un paragraphe test.</p>
    </div>
</template>

<script setup>
    import { ref } from 'vue'
    const message = ref('Hello World!')
</script>

<style scoped>

</style>