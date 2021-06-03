<template>
    <div class="page-category">

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