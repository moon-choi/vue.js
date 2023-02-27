<template>

 <!-- 모달창 -->
  <div class="black-bg" v-if="modal == true"> 
    <!-- if 조건식이 참일때만 밑이 나옴. -->
    <div class="white-bg">

    </div>
  </div>
  <div class="menu">
    <a v-for="(a) in nav" :key="a">{{ a }}</a>
  </div>

  <div>
    <img src="./assets/room0.jpg" class="room-img">
    <h4 @click="modal = true">{{listings[0]}}</h4>
    <p>1250 pounds</p>
    <button @click="nums[0] +=1">Report</button><span> Reported: {{ nums[0] }}</span>
  </div>
  <!-- @mouseover -->
  <!-- vue-on 은  @으로 대체 가능. event handler -->

  <div>
    <img src="./assets/room1.jpg" class="room-img">
    <h4>{{listings[1]}}</h4>
    <p>1300 pounds</p>
    <button @click="nums[1] +=1">Report</button><span> Reported: {{ nums[1] }}</span>
  </div>

  <div>
    <img src="./assets/room2.jpg" class="room-img">
    <h4>{{listings[2]}}</h4>
    <p>1100 pounds</p>
    <button @click="nums[2] +=1">Report</button><span> Reported: {{ nums[2] }}</span>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      modal: false,
      nums: [0, 0, 0],
      nav: ['Home', 'Shop', 'About'],
      listings: ['Canary Wharf', 'Bermondsey', 'Islington'],
      // styles: ['color: blue', 'color: red', 'color: green'],
    }
  },
  // 함수 만드는 공간
  methods: {
    increase() {
      this.nums += 1;
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
  width: 100%; height: 100%;
  background: rbga(0,0,0,0.5);
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
  width: 100%;
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
