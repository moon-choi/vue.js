<template>
  <div v-for="(property, i) in properties" :key="i">
    <img :src="property.image" class="room-img">
    <h4 @click="modal=true; opened=i">{{ property.title }}</h4>
    <p>{{ property.price }} pounds</p>
    <button @click="nums[i] += 1">Report</button><span> Reported: {{ nums[i] }}</span>
  </div>

</template>

<script>
export default {
    name: 'Card-banner',
}
</script>

<style></style>