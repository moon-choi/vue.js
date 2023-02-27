<template>
  <Modal :properties="properties" :opened="opened" :modal="modal"/>

  <Discount/>

  <Card :modal="modal" :opened="opened"/>

  <!-- @mouseover: vue-on 은  @으로 대체 가능. event handler -->
</template>

<script>
import listings from '../properties.js';
import Discount from './components/Discount.vue.js'; //1. import하기
import Modal from './components/Modal.vue.js';
import Card from './components/Card.vue';
// import Menu from './components/Menu.vue';

export default {
  name: "App",
  data() {
    return {
      properties: listings,
      modal: false,
      nums: [0, 0, 0, 0, 0],
      nav: ['Home', 'Shop', 'About'],
      listings: ['Canary Wharf', 'Bermondsey', 'Islington'],
      // styles: ['color: blue', 'color: red', 'color: green'],
    }
  },
  // 함수 만드는 공간
  methods: {
    close() {
      this.modal = false;
    }
  },
  // 2. 등록하기
  components: {
    Modal,
    Discount,
    Card,
    // Menu,
  },
};
</script>

<style>
body {
  margin: 0
}

div {
  box-sizing: border-box;
}

.discount {
  background: lightgrey;
  padding: 10px;
  margin: 10px;
  border-radius: 5px;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rbga(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

.room-img {
  width: 50%;
  margin-top: 40px;
}

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
