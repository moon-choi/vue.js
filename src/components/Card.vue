<template>
    <img :src="property.image" class="room-img" />
    <p>{{ property.title }}</p>
    <p>{{ property.price }} pounds</p>
    <!-- <button @click="nums[i] += 1">Report</button
    ><span> Reported: {{ nums[i] }}</span> -->
</template>

<script>
export default {
  props: {
    property: Object,
  }
  };
</script>

<style></style>
