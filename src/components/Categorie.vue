<template>
<section>
  <h1>Catégorie {{ categorieProp.name }}</h1>
  <input type="text" v-model="categorieProp.name">
  </section>
  
</template>

<script>
export default {
  name: "Categorie",
  props: {
    categorieProp: Object
  }
};
</script>

<style scooped>
section {
  margin: 5px;
  border: 2px solid black;
  background-color: salmon;

}
h1 {
  color: darkolivegreen;
}
</style>
