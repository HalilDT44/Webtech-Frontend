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
         fruits: []Add commentMore actions
          };
        },
        mounted() {
          const baseUrl = process.env.VUE_APP_BACKEND_BASE_URL;
          const endpoint = `${baseUrl}/api/fruits`; // ← ggf. ändern auf `/api/fruits` wenn du später andere Daten holst

          fetch(endpoint)
            .then(response => response.text())
            .then(data => {
              this.fruits = [data]; // oder JSON.parse(data) falls es ein Array ist
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
