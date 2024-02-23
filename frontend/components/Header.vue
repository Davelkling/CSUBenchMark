<script setup lang="ts">

</script>

<template>
    <div class="sticky top-0 h-12 ml-64 mr-64 bg-[#eeeeee] flex justify-between items-center">
        <div class="flex gap-8">
            <div class="flex items-center justify-center">
                <img src="/public/shield_logo.png" alt="logo" class="h-5 w-5 mr-1"/>
                <NuxtLink to="/">
                    <p class="text-xl">CSU BENCHMARK</p>
                </NuxtLink>
            </div>
            <NuxtLink to="/">
                <div class="flex">
                    <p class="text-xl">DASHBOARD</p>
                </div>
            </NuxtLink>
            
        </div>
        <div class="flex gap-8">
            <p class="text-xl">SIGN UP</p>
            <p class="text-xl">LOGIN</p>
        </div>
        
    </div>
</template>

<style scoped>

</style>