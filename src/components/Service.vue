<template>
    <h1>Service</h1>
    <div class="d-flex flex-wrap w-100 card-wrapper">
        <div class="card card-item" v-for="d in data" :key="d.id">
            <div class="card-body">{{ d.title }}</div>
        </div>
    </div>
</template>

<script setup>
import { ref, onMounted } from "vue"
const data = ref(null)

const fetchData = async () => {
    try {
        const response = await fetch("https://jsonplaceholder.typicode.com/posts")
        if (!response.ok) {
            throw new Error("Network response was not ok")
        }
        data.value = await response.json()
    } catch (error) {
        console.error("Fetch error:", error)
    }
}

onMounted(fetchData);
</script>

<style scoped>
.card-wrapper{
    gap:5px;
    margin-bottom: 10px;
    margin-top: 10px;
}
.card-item{
    width: calc(50% - 5px);
}
</style>