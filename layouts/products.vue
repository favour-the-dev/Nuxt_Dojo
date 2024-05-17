<template>
    <div class="container p-4 mx-auto">
        <div class="px-4 flex items-center justify-between w-full">
            <div class="text-2xl font-bold">
                <nuxt-link to="/Products">Our Products</nuxt-link>
            </div>
            <div class="flex gap-2 items-center">
                <nuxt-link to="/">Home</nuxt-link>
                <nuxt-link to="/About">About</nuxt-link>
            </div>
        </div>
        <div class="container p-4 mx-auto">
            <slot/>
        </div>
    </div>
</template>

<style>
    .router-link-exact-active{
        color: #12b488;
    }
</style>