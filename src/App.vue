<template>
  <div id="app">
    <Categorie
      v-for="categorie in categories"
      v-bind:key="categorie.id"
      v-bind:categorieProp="categorie"
    />
  </div>
</template>

<script>
import Categorie from "./components/Categorie";

export default {
  name: "App",
  data() {
    return {
      categories: null
    };
  },
  components: {
    Categorie
  },
  methods: {
    getCategories() {
      fetch("https://127.0.0.1:8000/api/categories", { method: "GET" })
        .then(response => response.json())
        .then(categorieJSON => {
          console.log(categorieJSON["hydra:member"]);
          this.categories = categorieJSON["hydra:member"];
        });
    }
  },
  mounted() {
    this.getCategories();
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
