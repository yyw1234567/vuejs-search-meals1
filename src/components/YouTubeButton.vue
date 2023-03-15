<template>
    <div>
        <a 
            href="href" 
            target="_blank"
            class="px-3 bg-red-500 rounded-md ml-3 hover:bg-green-500"
        >
            YouTube
        </a>
    </div>
</template>

<script setup>
    const props = defineProps({
        href: String
    })
</script>

