<template>
  <div class="container">
    <h1>Toggle to hover between Different state</h1>
    <img @click="on" v-if="!show" src="../assets/bulb-307687.svg" alt="" />
    <img @click="on" v-if="show" src="../assets/light-311119.svg" alt="" />
  </div>
</template>

<script>
  import { useToast } from "vue-toastification";
export default {
  data(){
    return{
      show: false
    }
  },
  setup(){
const toast = useToast();
return { toast }
  },
  methods:{
    on(){
      this.show = !this.show
      this.toast.error("I'm a toast!", {
  pauseOnFocusLoss: true,
  pauseOnHover: true,
  draggable: true,
  showCloseButtonOnHover: true,
  hideProgressBar: false,
  closeButton: "button",
  icon: true,
});
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