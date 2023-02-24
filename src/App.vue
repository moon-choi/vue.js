<template>
  <img alt="Vue logo" src="./assets/logo.png" />

  <div>
    <h4 class="red" :style="styles[0]">{{products[0]}}</h4>
    <p>{{ price1 }} pounds</p>
  </div>


  <div>
    <h4 class="red" :style="styles[1]">{{products[1]}}</h4>
    <p>{{ price2 }} pounds</p>
  </div>


  <div>
    <h4 class="red" :style="styles[2]">{{products[2]}}</h4>
    <p>{{ price3 }} pounds</p>
  </div>

</template>

<script>
export default {
  name: "App",
  data() {
    return {
      price1: 1250,
      price2: 1100,
      price3: 1300,
      products: ['Canary Wharf', 'Bermondsey', 'Islington'],
      styles: ['color: blue', 'color: red', 'color: green']
    }
  },
  components: {

  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
