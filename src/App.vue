<template>
  <convert-path></convert-path>
</template>

<script>
import ConvertPath from "./components/ConvertPath.vue";

export default {
  name: "App",
  components: {
    ConvertPath,
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
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

</style>
