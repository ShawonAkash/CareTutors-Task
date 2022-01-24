<template>
  <div class="container">
    <h1>Toggle to hover between Different state</h1>
    <img @click="on" v-if="!show" src="../assets/bulb-307687.svg" alt="" />
    <img @click="on" v-if="show" src="../assets/light-311119.svg" alt="" />
  </div>
</template>

<script>
export default {
  data(){
    return{
      show: false
    }
  },
  methods:{
    on(){
      this.show = !this.show
    }
  }
}
</script>

<style>
.container img {
  width: 300px;
  margin-left: 100px;
}
</style>