<template>
    <div>
        <div class="p-8">
            <input type="text" v-model="keyword" class="rounded border-2
                 border-gray-200 w-full" placeholder="Seach for Meals" @change="searchMeals" />
        </div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-5 p-8">
            <div v-for="meal of meals" :key="meal.idMeal" class="bg-white shadow-sm rounded-xl">
                <router-link :to="{name:'mealDetails', params:{id: meal.idMeal}}" >
                    <img :src="meal.strMealThumb" 
                    :alt="strMeal" 
                    class="rounded-t-xl w-full h-48 object-cover"
                    />
                </router-link>
                <div class="p-3">
                    <h3 class="px-3 py -2 flex justify-center font-bold">{{ meal.strMeal }}</h3>
                    <p>Perched atop OUE Bayfront on Collyer Quay, VUE presents a chef-driven menu that emphasises
                        binchotan-grilled specialities at the heart of its cuisine offerings</p>
                    <div class=" flex justify-between ">
                        <YouTubeButton :href="meal.strYoutube"/>
                        <router-link to="/" class="px-3 bg-orange-500  mr-3 rounded-md hover:bg-green-500">
                            view
                        </router-link>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { computed, onMounted, ref } from "vue";
import { useRoute } from "vue-router";
import store from "../store";
import YouTubeButton from '../components/YouTubeButton.vue'



const route = useRoute();
const keyword = ref('');
const meals = computed(() => store.state.searchedMeals);

function searchMeals() {
    store.dispatch('searchMeals', keyword.value)
}

onMounted(() => {
  keyword.value = route.params.name
  if(keyword.value) {
    searchMeals();
  }
})
</script>

