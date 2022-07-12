<template>
  <table id="table">
    <tr>
      <td>Original Windows File Path</td>
      <td colspan="3">
        <textarea
          name="windowsLocation"
          id="windowsLocation"
          placeholder="Enter or paste Windows file path here"
          rows="10"
          cols="50"
          required
          v-model="originalText"
        ></textarea>
      </td>
    </tr>
    <tr>
      <td></td>
      <td colspan="3" id="textDisplay"></td>
    </tr>
    <tr id="filepath">
      <td colspan="4"><strong>New Mac File Path:</strong></td>
    </tr>
    <tr>
      <td colspan="4">
        <h4 id="windowsLocation">{{ convertedText }}</h4>
      </td>
    </tr>

    <tr>
      <td><button @click="clearAll()">Clear</button></td>
      <td colspan="2" />
      <td>
        <button
          type="button"
          @click="copyText()"
          style="margin-left: 10px"
          id="copyButton"
        >
          Copy Mac File Path to clipboard
        </button>
      </td>
    </tr>
  </table>
</template>

<script>
export default {
  name: "WindowsPath",
  data() {
    return {
      originalText: "",
      convertedText: "",
    };
  },
  watch: {
    originalText() {
      this.convertedText = this.originalText.replaceAll("\\", "/");
      if (this.convertedText.includes(":")) {
        this.convertedText = this.convertedText.split(":");
        this.convertedText = this.convertedText[1];
      }
    },
  },
  methods: {
    clearAll() {
      this.originalText = "";
    },
    copyText() {
      navigator.clipboard.writeText(this.convertedText);

      /* Alert the copied text */
      alert("Copied the text to the clipboard: " + this.convertedText);
    },
  },
};
</script>

<style scoped>
body,
h1,
p {
  font-family: "Franklin Gothic Medium", Arial, sans-serif;
}

a.navbar-brand {
  white-space: normal;
  text-align: center;
  word-break: break-all;
}

a {
  color: #0366d6;
}

input {
  margin: 2px;
}

label {
  font-style: italic;
  font-weight: bolder;
}

textarea {
  margin: 2px;
}

html {
  font-size: 14px;
}

@media (min-width: 768px) {
  html {
    font-size: 16px;
  }
}

button.accept-policy {
  font-size: 1rem;
  line-height: inherit;
}

html {
  position: relative;
  min-height: 100%;
}

body {
  /* Margin bottom by footer height */
  margin-bottom: 60px;
  margin-left: 10%;
  margin-right: 10%;
}

/* #copyButton {
  display: none;
} */

#table {
  margin: 0 auto;
}
button {
  margin-top: 20px;
}
</style>