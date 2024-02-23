<script setup lang="ts">
import { ref } from 'vue';

const start = ref(false);
const next = ref(false);

function startGame() {
    start.value = true;
}

function clicked(){
    
    next.value = true;
}

function finished(){
    start.value = false;
    next.value = false;
}

</script>

<template>
    <div class="flex flex-col bg-[#eeeeee]">
        <div class="container mx-auto">
            <Header/>
        </div>
        <button v-if="start" @click="" class="w-full h-[34rem] bg-red-500">
            <div class="flex flex-col justify-center items-center h-full">
                <span class="material-symbols-outlined text-white text-8xl font-bold">more_horiz</span>
                <p class="text-[#fafafa] text-7xl font-semibold mb-24">Waiting for green</p>
            </div>
        </button>
        <div v-else="start" class="w-full h-[34rem] bg-[#009378]">
            <div class="container mx-auto flex flex-col justify-center items-center h-full">
                <img src="/public/reaction_white.png" alt="reaction" class="w-32 h-32 mb-8">
                <p class="text-[#fafafa] text-7xl font-semibold mb-2">Reaction Time Test</p>
                <p class="text-[#fafafa] text-xl">When the red box turns green, click as quickly as you can.</p>
                <button @click="startGame" class="bg-[#EAB64D] p-2 m-8 rounded-sm w-36 font-semibold">Get Started</button>
            </div>
        </div>
        
        <div class="container mx-auto flex-grow bg-[#eeeeee]">
            <Games/>
        </div>
    </div>
</template>

<style scoped>

</style>