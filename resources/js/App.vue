<script setup>
import axios from 'axios';
import { onMounted, ref } from 'vue';

const products = ref([]);

onMounted( () => {
    axios.get('api/products')
    .then(response => products.value = response.data);
})
</script>

<template>
    <strong>I am a Vue App in Laravel</strong>
    <div v-for="product in products">
    {{  product.id  }}  : {{  product.title  }}
    </div>
</template>