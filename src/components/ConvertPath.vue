<template>
  <div>
    <h1>Convert Your File Path</h1>
    <p>This will convert a Mac file path to a Windows file path</p>
    <p>
      For example:
      <b>
        smb://production.ctv.ca/storage/CreativeAgency/QSCreative/Public/Delivery/Starz/</b
      >
    </p>
    <p>
      Converts to:
      <b>
        \\production.ctv.ca\storage\CreativeAgency\QSCreative\Public\Delivery\Starz\</b
      >
    </p>
    <p id="macpath">
      <MacPath />
    </p>
  </div>
</template>

<script>
import MacPath from "./MacPath.vue";

export default {
  name: "ConvertPath",
  components: { MacPath },
};
</script>

<style scoped>
#macpath,
#windowspath {
  margin: 0 auto;
}

hr {
  width: 75%;
}
</style>