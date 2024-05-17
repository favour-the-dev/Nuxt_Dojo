<template>
    <div class="container p-4 mx-auto">
        <div class="px-4">
            <div class="text-2xl font-bold">
                <nuxt-link to="/Products">Our Products</nuxt-link>
            </div>
        </div>
        <div class="container p-4 mx-auto">
            <slot/>
        </div>
        <footer class="flex flex-col font-bold container p-4 mx-auto">
            <nuxt-link to="/">Home</nuxt-link>
            <nuxt-link to="/About">About</nuxt-link>
        </footer>
    </div>
</template>

<style>
    .router-link-exact-active{
        color: #12b488;
    }
</style>