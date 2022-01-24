<template>
<div v-for="(a,i) in rooms" :key="i">
    <img :src="rooms[i].image" class="room-img">
    <h4 @click="$emit('openModal');now=i">{{rooms[i].title}}</h4>
    <p>{{rooms[i].price}}</p>
    
  </div>

</template>

<script>
export default {
    name:'Card',
    props:{
        rooms:Object,
    }
}
</script>

<style>

</style>