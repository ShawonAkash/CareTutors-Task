<template>
  <div class="navbar">
    <img class="logo" src="../assets/logo2.png" />
    <a href="#" @click="toggleComponent1">Assignment 1</a>
    <a href="#" @click="toggleComponent2">Assignment 2</a>
  </div>
</template>

<script>
export default {
  methods:{
    toggleComponent1(){
      this.$emit('close1')
    },
    toggleComponent2(){
      this.$emit('close2')
    }
  }
}
</script>

<style>
</style>