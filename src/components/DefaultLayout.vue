<template>
    <div class="bg-gray-200 h-full">
        <Navbar/>
        <main>
            <router-view/>
        </main>
    </div>
</template>

<script setup>
import Navbar from './Navbar.vue'
</script>