<template>
    <div>
        <h1>HOME PAGE</h1>
        <router-link to="/test">
            Página de Teste
        </router-link>
        <button @click.prevent="getValue">
            Trigger Endpoint
        </button>
        <p v-if="response">
            {{ response.data }}
        </p>
    </div>
</template>

<script setup>
import axios from "axios";
import { ref } from "vue";

const response = ref();

const getValue = async () => {
    try {
        response.value = await axios.get("/api/test-me")
    } catch(error) {
        console.log(error)
    }
}
</script>
