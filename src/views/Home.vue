<template>
    <div class="flex flex-col justify-center p-8">
       

        <div class="flex gap-3 justify-center mt-2">
            <router-link :to="{name:'byLetter', params:{letter}}" v-for="letter of letters">
                {{ letter }}
            </router-link>
        </div>
    </div>
</template>


<script setup>
import { computed, onMounted, ref } from 'vue';
import store from '../store';
import axiosClient from '../axiosClient.js';


// const meals = computed(() => store.state.meals);
const letters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'.split("");
const ingredients = ref([])

onMounted(async() => {
    const response = await axiosClient.get('/list.php?i=list')
    console.log(response.data)
    ingredients.value = response.data 
})
</script>

