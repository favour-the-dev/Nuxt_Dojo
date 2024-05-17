<template>
    <div>
        <div class="grid grid-cols-2 lg:grid-cols-4 gap-2 lg:gap-4">
            <nuxt-link :to="`/products/${product.id}`" class="p-3 relative shadow-sm border border-[#12b488] border-opacity-50 rounded-md flex flex-col gap-1" v-for="(product, index) in products" :key="index">
                <div class="w-full h-32 md:h-44">
                    <img :src="product.image" :alt="product.title" class="w-full h-full object-fit">
                </div>
                <p class="text-sm text-[#12b488] font-semibold">{{ product.title }}</p>
                <span class="text-xs capitalize">{{ product.category }}</span>
                <span class="">${{ product.price }}</span>
                <button class="btn">Add to Cart</button>
            </nuxt-link>
        </div>
    </div>
</template>

<script>
    definePageMeta({
        layout: 'products'
    })

    export default{
        data() {
            return {
                products: []
            }
        },
        async created(){
            try{
                const products = await useFetch('https://fakestoreapi.com/products');
                this.products = products.data._value
            }catch(error){
                console.log(products)
            }
        }
    }
</script>