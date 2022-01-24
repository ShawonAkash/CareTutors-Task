<template>
  <Navbar @close1="toggleComponent1" @close2="toggleComponent2" />
  <Bulb v-if="show" />
  <Listview v-else />
</template>

<script>
import Navbar from "@/components/Navbar.vue"
import Listview from "@/components/Listview.vue"
import Bulb from "@/components/Bulb.vue"

export default {
  name: "Home",
  components: {
    Navbar,
    Listview,
    Bulb
  },
  data(){
    return{
      show: true
    }
  },
  methods:{
    toggleComponent1(){
    this.show= true
    console.log(this.show);
  },
    toggleComponent2(){
    this.show= false
    console.log(this.show);
  }
  }
}
</script>
