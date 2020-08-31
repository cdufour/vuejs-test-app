<template>
    <div>
        <span>{{ fruit.name }} ({{ fruit.origin }})</span>
        <button @click="remove(fruit.name)">Remove</button>
    </div>
</template>

<script>
    export default {
        props: {
            fruit: Object
        },
        methods: {
            remove(fruitName) {
                //console.log('remove', fruitName)
                this.$emit('remove', fruitName)
            }
        }
    }
</script>

<style scoped>

</style>