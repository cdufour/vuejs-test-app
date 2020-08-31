<template>
    <div>
        <h1>Component B (Liste des fruits)</h1>
        <!-- <ul>
            <li 
                v-for="(fruit, index) in fruits" 
                :key="index">{{ fruit.name }} ({{ fruit.origin }})</li>
        </ul> -->
        <Fruit
            v-for="(fruit, index) in fruits"
            :key="index"
            :fruit="fruit" 
            v-on:remove="removeFruit"
            />

    </div>
</template>

<script>
    import Fruit from './Fruit'
    export default {
        props: {
            fruits: Array
        },
        data: function() {
            return { title: 'Composant B' }
        },
        components: { Fruit },
        methods: {
            removeFruit(fruitName) {
                this.$emit('removeFruit', fruitName)
            }
        }
    }
</script>

<style scoped>

</style>