<template>
  <div>
    <h1>Meine Früchte</h1>
    <ItemList :items="fruits" />
  </div>
</template>

<script>
import ItemList from './components/ItemList.vue'

export default {
  name: 'App',
  components: {
    ItemList
  },
  data() {
    return {
      fruits: ['Apfel', 'Banane', 'Kirsche']
    }
  }
}
</script>

<style scoped>
h1 {
  font-family: Arial, sans-serif;
}
</style>
