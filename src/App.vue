<template>
  <h1>{{ title }}</h1>
  <input type="text" ref="name" @keypress.enter="handlerEvent" />
  <button @click="handlerEvent">show name</button>
  <br />
  <button @click="handlerBox">showBox</button>
  <h2 ref="showNwme"></h2>
  
  <!--   21   -->
  <div v-show="showBox">
    <Model theme="sale" @close="handlerBox">
      <h1>aliakbargh text header</h1>
      <p>aliakbar text header</p>
      <template v-slot:linkss> 
        <a href="#">ananas</a>
        <a href="#">ananas2</a>
      </template>
    </Model>
  </div>

</template>



<script>
import Model from "./components/M-C.vue";
export default {
  name: "App",
  components: { Model },
  data() {
    return {
      theme: "sale",
      title: "aliakbar vue",
      showBox: true,
    };
  },
  methods: {
    handlerEvent() {
      console.log(this.$refs.name);
      this.$refs.showNwme.innerHTML = this.$refs.name.value;
      this.$refs.name.value = "";
    },
    handlerBox() {
      this.showBox = !this.showBox;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  color: cadetblue;
}
</style>
<!-- <div v-show="showBox" @click="handlerBox">
    <Model :headert="header" :textp="text" theme="sale"/>
  </div>21  -->
  <!-- <div v-show="showBox">
    <Model  :headert="header" :textp="text" theme="sale" @close="handlerBox" />
  </div> 
   data() {
    return {
      header: "aliakbar test box",
      text: "aliakbar test",
      theme: "sale",
      title: "aliakbar vue",
      showBox: true,
    };
  },
  methods: {
    handlerEvent() {
      console.log(this.$refs.name);
      this.$refs.showNwme.innerHTML = this.$refs.name.value;
      this.$refs.name.value = "";
    },
    handlerBox() {
      this.showBox = !this.showBox;
    },
  },
};
</script>

  
  21-->
  