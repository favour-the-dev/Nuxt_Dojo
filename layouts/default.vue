<template>
    <div class="container p-4 mx-auto">
        <div class="flex justify-between px-4 items-center text-gray-500">
            <div class="">
                <nuxt-link to="/" class="text-2xl font-bold text-[#12b488]">Shoppify</nuxt-link>
            </div>
            <div class="flex gap-2 items-center">
                <nuxt-link to="/">Home</nuxt-link>
                <nuxt-link to="/about">About</nuxt-link>
                <nuxt-link to="/products" class="btn">Products</nuxt-link>
            </div>
        </div>
        <div class="container mx-auto p-4">
            <slot/>
        </div>
    </div>
</template>

<style>
    .router-link-active{
        color: #12b488;
    }
</style>