<template>

  <div class="menu">
    <a v-for="(a) in navs" :key="a">{{ a }}</a>
  </div>

  <div>
    <h4 v-for="
      (listing, i) in listings" :key="listing"
      class="red">{{i}}: {{listing}} pounds</h4>
      <button @click= "increase">Report</button><span> Reported: {{ num }}</span>
      <!-- @mouseover -->
  </div>

</template>

<script>
export default {
  name: "App",
  data() {
    return {
      num: 0,
      nav: ['Home', 'Shop', 'About'],
      listings: {
        'Canary Wharf': 1250,
        'Bermondsey': 1300,
        'Islington': 1100,
      },
      styles: ['color: blue', 'color: red', 'color: green'],
    }
  },
  // 함수 만드는 공간
  methods: {
    increase(){
      this.num += 1;
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
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 5px;
}
</style>
