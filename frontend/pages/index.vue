<script setup lang="ts">

</script>

<template>
    <div class="bg-[#eeeeee]">
        <div class="flex flex-col">
            <div class="container mx-auto ">
                <Header/>
            </div>
            
            <div class="w-screen h-[34rem] bg-[#009378]">
                <div class="container mx-auto flex flex-col justify-center items-center h-full">
                    <img src="/public/shield_logo2.png" alt="hero_image" class="w-32 h-32 mb-8">
                    <p class="text-[#fafafa] text-7xl font-semibold mb-2">CSU Benchmark</p>
                    <p class="text-[#fafafa] text-xl">Compete with your peers with brain games and cognitive tests</p>
                    <button class="bg-[#EAB64D] p-2 m-8 rounded-sm w-36 font-semibold">Get Started</button>
                </div>
            </div>
            <div class="container mx-auto bg-[#eeeeee]">
                <Games/>
            </div>
        </div>
        
    </div>
</template>

<style scoped>

</style>