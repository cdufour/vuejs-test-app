<template>
  <div id="app">
    <ComponentA v-on:addFruit="updateFruits" />
    <ComponentB 
      :fruits="fruits" 
      v-on:removeFruit="removeFruit" />
  </div>
</template>

<script>
import ComponentA from './components/ComponentA'
import ComponentB from './components/ComponentB'

export default {
  name: 'App',
  data: function() {
    return {
      fruits: []
    }
  },
  components: {
    ComponentA, ComponentB
  },
  methods: {
    updateFruits(fruit) {
      //console.log('updateFruits', fruit)
      this.fruits.push(fruit);
    },
    removeFruit(fruitName) {
      this.fruits = 
        this.fruits.filter(fruit => fruit.name !== fruitName)
    }
  }
}
</script>

<style>
</style>
