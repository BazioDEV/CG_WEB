<template>
    <div class="page-category">
        <div class="columns is-multiline">
            <div class="column is-12">
                <h2 class="is-size-2 has-text-centered">{{ category.name }}</h2>
            </div>
            <div class="column is-3" v-for='product in category.products' v-bind:key='product.id'>
                <div class="box">
                    <figure class="image mb-4">
                        <img :src="product.get_thumbnail">
                    </figure>
                    <h3 class="is-size-4">{{ product.name }}</h3>
                    <p class="is-size-6 has-text-grey">${{ product.price }}</p>

                    <router-link v-bind:to="product.get_absolute_url" class="button is-dark mt-4">View detail</router-link>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
import { toast } from 'bulma-toast'
    export default {
        name: 'Category',
        data() {
            return {
                category: {
                    products: []
                }
            }
        },
        mounted() {
            this.getCategory()
        },
        methods: {
            async getCategory() {
                const categorySlug = this.$route.params.category_slug

                this.$store.commit('setIsLoading', true)

                axios.get(`/api/v1/products/${categorySlug}`)
                    .then(response => {
                        this.category = response.data

                        document.title = this.category.name + ' | Clover Glove'
                    })
                    .catch(error => {
                        console.log(error)

                        toast({
                            message: 'Something went wrong. Please try again!!!',
                            type: 'is-danger',
                            dismissible: true,
                            pauseOnHover: true,
                            duration: 2000,
                            position: 'top-center',
                        })
                    })

                    this.$store.commit('setIsLoading', false)
            }
        }

    }
</script>

<style lang="scss" scoped>

</style>