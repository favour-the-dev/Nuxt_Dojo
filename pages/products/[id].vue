<template>
    <div class="p-2 flex flex-col space-y-6">
        <div class="flex gap-2 items-start md:items-center text-sm md:text-base">
            <nuxt-link to="/products" class="text-lg text-gray-500 whitespace-nowrap">Product ></nuxt-link>
            <nuxt-link :to="`/products/${this.product.id}`">{{ product.title }}</nuxt-link>
        </div>
        <div class="container mx-auto w-full flex flex-col md:flex-row items-center gap-2 justify-between">
            <div class="w-full md:w-1/2 h-[300px] md:h-[400px]">
                <img :src="product.image" alt="" class="w-full h-full object-fill">
            </div>
            <div class="w-1/2">
                <h2 class="font-bold text-[#12b488] text-2xl">{{ product.title }}</h2>
                <h3 class="capitalize font-semibold text-sm">{{ product.category }}</h3>
                <h3 class="font-bold text-[#12b488] text-xl">${{ product.price }}</h3>
                <div class="font-semibold">
                    <p>{{product.description}}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data(){
            return {
                product: [],
            }
        },
        async created(){
            try{
                const product = await useFetch(`https://fakestoreapi.com/products/${this.$route.params.id}`)
                this.product = product.data._value;
                console.log(this.product);
            }catch(error){
                console.log(error)
            }
        }
    }
</script>

<style>

</style>