<script setup>
import axios from 'axios'
import {onMounted, ref} from "vue";
import { useRoute } from "vue-router";

const route = useRoute();
const data = ref();
onMounted(async () => {
    const res = await axios.get(`http://localhost:8080/api/items/${route.params.id}`)
    data.value = res.data
})
</script>
<template>
{{ data }}
</template>
<style scoped></style>