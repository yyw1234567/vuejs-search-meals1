<template>
    <header class="bg-white shadow-sm h-16 flex justify-between">
        <router-link :to="{ name: 'home' }" class="inline-flex items-center hover:bg-red-500 rounded-sm px-5">
            Home
        </router-link>
        <div>
            <router-link :to="{ name: 'byName' }"
                class="px-2 h-full hover:bg-purple-500 rounded-sm inline-flex items-center">
                Search Meals
            </router-link>
            <router-link :to="{ name: 'byLetter' }"
                class="px-2 h-full hover:bg-purple-500 rounded-sm inline-flex items-center">
                Search By Letter
            </router-link>
            <router-link :to="{ name: 'byIngredient' }"
                class="px-2 h-full hover:bg-purple-500 rounded-sm inline-flex items-center">
                Search By Ingredients
            </router-link>
        </div>
    </header>
</template>