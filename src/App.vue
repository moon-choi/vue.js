<template>
  <!-- 모달창 -->
  <div class="black-bg" v-if="modal == true">
    <!-- if 조건식이 참일때만 밑이 나옴. -->
    <div class="white-bg">
      <button @click="close"> X </button>
      <h4>{{ properties[opened].title }}</h4>
      <p>{{ properties[opened].content }}</p>
      <p>{{ properties[opened].price}} pounds</p>
    </div>
  </div>

  <div class="menu">
    <a v-for="(link) in nav" :key="link">{{ link }}</a>
  </div>

  <div v-for="(property, i) in properties" :key="i">
    <img :src="property.image" class="room-img">
    <h4 @click="modal = true; opened=i">{{ property.title }}</h4>
    <p>{{ property.price }} pounds</p>
    <button @click="nums[i] += 1">Report</button><span> Reported: {{ nums[i] }}</span>
  </div>

  <!-- @mouseover: vue-on 은  @으로 대체 가능. event handler -->
</template>

<script>
import data from './properties.js'

export default {
  name: "App",
  data() {
    return {
      properties: data,
      modal: false,
      nums: [0, 0, 0, 0, 0],
      nav: ['Home', 'Shop', 'About'],
      listings: ['Canary Wharf', 'Bermondsey', 'Islington'],
      // styles: ['color: blue', 'color: red', 'color: green'],
    }
  },
  // 함수 만드는 공간
  methods: {
    // increase() {
    //   this.nums += 1;
    // },
    close() {
      this.modal = false;
    }
  },
  components: {
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
