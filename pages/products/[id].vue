<template>
    <div class="p-2 flex flex-col gap-2">
        <div class="flex gap-2 items-center">
            <nuxt-link to="/products" class="text-lg text-gray-500">Product ></nuxt-link>
            <nuxt-link :to="`/products/${this.product.id}`">{{ product.title }}</nuxt-link>
        </div>
        <div class="container mx-auto w-full flex items-center gap-2 justify-between">
            <div class="w-full md:w-1/2 h-[500px]">
                <img :src="product.image" alt="" class="w-full h-full object-fill">
            </div>
            <div></div>
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