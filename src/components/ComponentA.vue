<template>
    <div>
        <h1>Component A (Formulaire)</h1>
        <div>
            <input v-model="fruitName" type="text" placeholder="Nom du fruit"/>
            <input v-model="fruitOrigin" type="text" placeholder="Origine du fruit"/>
            <button @click="saveFruit">Enregistrer</button>
        </div>
    </div>
</template>

<script>
    export default {
        data: function() {
            return {
                fruitName: '',
                fruitOrigin: ''
            }
        },
        methods: {
            saveFruit() {
                var fruit = {
                    name: this.fruitName, 
                    origin: this.fruitOrigin
                };
                this.$emit('addFruit', fruit)
            }
        }
    }
</script>

<style scoped>

</style>