<template>
        <div class="convertinfo-container">
            <h1>Convert Your File Path</h1>
            <p>This will convert a Mac file path to a Windows file path</p>
            <h3>For example:</h3>
            <span class="url">
                <b>smb://production.ctv.ca/storage/CreativeAgency/QSCreative/Public/Delivery/Starz/</b>
            </span>
            <h3>Converts to:</h3>
            <span class="url">
            <b>\\production.ctv.ca\storage\CreativeAgency\QSCreative\Public\Delivery\Starz\</b>
            </span>
        </div>
</template>

<script>
    export default {
        name: "ConvertInfo"
    }
</script>

<style scoped>
body,
h1,
p {
  font-family: "Franklin Gothic Medium", Arial, sans-serif;
}

h1,
h3 {
    color: darkgreen;
}
.convertinfo-container {
    text-align: center;
    justify-content: center;
    margin: 0 auto 20px;
    padding: 0 20px;
}
.url {
    word-break: break-all;
    word-wrap: break-word;
}

@media (min-width: 650px) {
    .convertinfo-container {
        width: 100%;
    }
    .url {
        word-break: normal;
        word-wrap: normal;
    }
}


</style>