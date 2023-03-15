<template>
    <div class="flex flex-col justify-center p-8">
        <div>
            <input type="text"  class="rounded border-2 border-gray-200 w-full"
             placeholder="Seach for Meals"/>
        </div>

        <div class="flex gap-3 justify-center mt-2">
            <router-link to="/" v-for="letter of letters">
                {{ letter }}
            </router-link>
            
        </div>
    </div>
</template>

<script setup>
import { computed } from 'vue';
import store from '../store';

const meals = computed(() => store.state.meals);
const letters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'.split("");
</script>

