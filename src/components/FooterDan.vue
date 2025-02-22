<template>
  <div class="copyright-container">
    <span class="copyright"
      >&copy;<a href="https://dansanpedro.com" target="_blank" class="link"
        >Daniel San Pedro</a
      >
      , {{ new Date().getFullYear() }}</span
    >
  </div>
</template>

<script>
export default {
  Name: "FooterDan",
};
</script>

<style scoped>
.copyright-container {
  text-align: center;
  justify-content: center;
  margin: 0 auto 20px;
  padding: 0 20px;
}
.copyright {
  margin: 0 auto;
}
.link {
  text-decoration: none;
}
a:hover {
  color: darkgreen;
}

@media (min-width: 650px) {
  .copyright-container {
    width: 100%;
    margin: 0 auto;
  }
}
</style>
