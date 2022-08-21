<template>
    <div class="main">
      <convert-info />
      <hr>
      <mac-path />
      <footer-dan />
    </div>
</template>

<script>
import MacPath from "./MacPath.vue";
import ConvertInfo from "./ConvertInfo.vue";
import FooterDan from "./FooterDan.vue"

export default {
  name: "ConvertPath",
  components: { 
    MacPath,
    ConvertInfo,
    FooterDan
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
  margin: 0 auto;
}
hr {
  width: 50%;
  max-width: 500px;
}
.convert {
  margin: 0 auto;
}
</style>