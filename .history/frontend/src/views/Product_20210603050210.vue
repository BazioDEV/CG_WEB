<template>
    <div class="page-product">
        <div class="columns is-multiline">
            <div class="column is-9">
                <figure class="image mb-6">
                    <img :src="product.get_image" >
                </figure>

                <h1 class="title">{{ product.name }}</h1>
                <p>{{ product.description }}</p>
            </div>
            <div class="column is-3">
                <h2 class="subtitle">Information</h2>
                <p><strong>Price: </strong>${{ product.price }}</p>

                <div class="field has-addons mt-6">
                    <div class="control">
                        <input type="number" class="input" min="1" v-model="quantity">
                    </div>
                    <div class="control">
                        <a class="button is-dark">Add to cart</a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import axios from 'axios'
    export default {
        name: 'Product',
        data() {
            return {
                product: {},
                quantity: 1
            }
        },
        mounted() {
            this.getProduct()
        },
        methods: {
            getProducts() {
                const category_slug = this.$route.params.category_slug
                const product_slug = this.$route.params.product.slug
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>