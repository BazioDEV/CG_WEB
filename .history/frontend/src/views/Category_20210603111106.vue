<template>
    <div class="page-category">
        <div class="columns is-multiline">
            <div class="column is-12">
                <h2 class="is-size-2 has-text-centered">{{ category.name }}</h2>
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
        }

    }
</script>

<style lang="scss" scoped>

</style>