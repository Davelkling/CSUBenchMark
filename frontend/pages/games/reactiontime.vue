<script setup lang="ts">
import { ref } from 'vue';

const red = ref<boolean>(false);
const next = ref<boolean>(false);
let startSecond = ref<number>(0);
let endSecond = ref<number>(0);
let games = ref<number[]>([])
let counter = ref<number>(0);
let green = ref<boolean>(false);
let isFinish = ref<boolean>(false)
let isBeforeStart = ref<boolean>(true)
let gameResult = ref<boolean>(false)
let result = ref<number>(0);

function print(){
    console.log("test");
}

function print2(){
    console.log("test2");
}

function redGame() {
    isBeforeStart.value = false;
    green.value = false;
    red.value = true;
    let randomIndex: number = 0;
    randomIndex = 1000 + Math.floor(Math.random() * 9000);
    
    setTimeout(() => {
        console.log(randomIndex)
        red.value = false;
        green.value = true;
        startSecond.value = Date.now();
    }, randomIndex);

}

function clicked(){
    while(counter.value){
        endSecond.value = Date.now();
        result.value = endSecond.value - startSecond.value;
        games.value.push(result.value);

        console.log(games.value);
        
        counter.value++;
        gameResult.value = true;
        if(counter.value == 4){
            counter.value = 0;
            finished();
        }
    }
}

function finished(){
    isFinish.value = true;
    counter.value = 0;
    games.value = [];
    red.value = false;
}

</script>

<template>
    <div class="flex flex-col bg-[#eeeeee]">
        <div class="container mx-auto">
            <Header/>
        </div>
        
        <div v-if="isBeforeStart" class="w-full h-[34rem] bg-[#009378]">
            <div class="container mx-auto flex flex-col justify-center items-center h-full">
                <img src="/public/reaction_white.png" alt="reaction" class="w-32 h-32 mb-8">
                <p class="text-[#fafafa] text-7xl font-semibold mb-2">Reaction Time Test</p>
                <p class="text-[#fafafa] text-xl">When the red box turns green, click as quickly as you can.</p>
                <button @click="redGame" class="bg-[#EAB64D] p-2 m-8 rounded-sm w-36 font-semibold">Get Started</button>
            </div>
        </div>
        <button v-else-if="red" class="w-full h-[34rem] bg-red-500">
            <div class="flex flex-col justify-center items-center h-full">
                <span class="material-symbols-outlined text-white text-8xl font-bold">more_horiz</span>
                <p class="text-[#fafafa] text-7xl font-semibold mb-24">Waiting for green</p>
            </div>
        </button>   
        <button v-else-if="green" @click="clicked" class="w-full h-[34rem] bg-[#009378]">
            <div class="flex flex-col justify-center items-center h-full">
                <p class="text-[#fafafa] text-7xl font-semibold mb-24">Click fast!</p>
            </div>
        </button>
        <button v-else-if="gameResult" @click="green = true" class="w-full h-[34rem] bg-[#009378]">
            <div class="flex flex-col justify-center items-center h-full">
                <p class="text-[#fafafa] text-7xl font-semibold mb-24">{{  }}</p>
                <p class="text-[#fafafa] text-7xl font-semibold mb-24">DONE</p>
            </div>
        </button>
        
        
        <div class="container mx-auto flex-grow bg-[#eeeeee]">
            <Games/>
        </div>
    </div>
</template>

<style scoped>

</style>