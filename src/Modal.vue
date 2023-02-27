<template>
    <div class="black-bg" v-if="modal == true">
        <!-- if 조건식이 참일때만 밑이 나옴. -->
        <div class="white-bg">
            <img :src="properties[opened].image" style="width:100%">
            <h4>{{ properties[opened].title }}</h4>
            <p>{{ properties[opened].content }}</p>
            <p>{{ properties[opened].price }} pounds</p>
            <button @click="close"> X </button>

        </div>
    </div>
</template>

<script>
export default {
    name: 'Modal-banner',
}
</script>

<style></style>



