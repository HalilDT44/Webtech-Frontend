<template>
  <div>
    <h1>Meine Früchte</h1>
    <ItemList :items="fruits" />
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      fruits: []
    };
  },
  mounted() {
    const baseUrl = process.env.VUE_APP_BACKEND_BASE_URL;
    const endpoint = `${baseUrl}/api/fruits`;

    fetch(endpoint)
          .then(response => response.json()) // ✅ richtige Methode
          .then(data => {
            this.fruits = data; // ✅ direkt zuweisen
          })
          .catch(error => {
            console.error('Fehler beim Laden der Daten:', error);
          });
  }
};
</script>


<style scoped>
h1 {
  font-family: Arial, sans-serif;
}
</style>
