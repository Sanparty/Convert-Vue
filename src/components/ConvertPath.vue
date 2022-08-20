<template>
    <div class="main">
      <convert-info />
      <hr>
      <mac-path />
    </div>
</template>

<script>
import MacPath from "./MacPath.vue";
import ConvertInfo from "./ConvertInfo.vue";

export default {
  name: "ConvertPath",
  components: { 
    MacPath,
    ConvertInfo
  },
};
</script>

<style>
.main {
  display: flex;
  flex-direction: column;
  text-align: center;
  align-items: center;
  justify-content: center;
  width: 100%;
}
hr {
  width: 50%;
}
.convert {
  margin: 0 auto;
}
</style>