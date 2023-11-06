<template>
    <header>
            <h1>
                <img src="../assets/logo.svg" alt="/">
            </h1>
        </header> 
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'BarraLateral'
})
</script>

<style scoped>
    header {
        background: #030f2e;
        width: 100%;
        height: 100vh;
    };

    @media only screen and (max-width: 768px) {
        header {
            padding: 2.5rem;
            height: auto;
        }
    };

    img {
        margin-top: 5rem;
    };
</style>