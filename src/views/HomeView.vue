<script>
import axios from 'axios';
export default {
  data: function() {
    return {
      message: "Welcome to Vue.js!!!!",
      subheading: "here are some items to buy:",
      products: []
    };
  },
  created: function() {
    console.log('in create');
    axios.get('http://localhost:3000/products.json').then(response => {
      console.log(response.data);
      this.products = response.data;
    });
  },
  methods: {}
};
</script>

<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <h2>{{ subheading }}</h2>
    <div v-for="product in products">
      {{ product.id }}
      {{ product.name }}
    </div>

  <input type="text">
  <button v-on:click=""></button>



  </div>
</template>

<style>
h2 {
  color: red;
  font-style: italic;
}
</style>