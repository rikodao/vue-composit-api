<template>
  <div class="home">
    <Parent msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from "@/components/HelloWorld.vue";
import Parent from "@/components/ParentComponent.vue";
export default {
  name: "home",
  components: {
    // HelloWorld,
    Parent
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
