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
