<template>
  <div class="convert-container">
      <div>
        <div><strong>Original Mac File Path:</strong></div>
        <div>
          <textarea
            name="macLocation"
            id="macLocation"
            placeholder="Enter or paste Mac file path here"
            rows="5"
            cols="75"
            required
            v-model="originalText"
          ></textarea>
        </div>
      </div>
      <div>
        <div id="textDisplay"></div>
        <div id="filepath">
          <div v-if="convertedText"><strong>New Windows File Path:</strong></div>
        </div>
        <div id="newPath">
          <div id="windowsLocation">{{ convertedText }}</div>
        </div>
        <div v-if="convertedText">
          <button
            type="button"
            @click="copyText()"
            style="margin-left: 10px"
            id="copyButton"
          >
            Copy Windows File Path to clipboard
          </button>
        </div>
        <div v-if="convertedText || originalText"><button @click="clearAll()">Clear</button></div>
      </div>
  </div>
</template>

<script>
export default {
  name: "MacPath",
  data() {
    return {
      originalText: "",
      convertedText: "",
    };
  },
  watch: {
    originalText() {
      this.convertedText = this.originalText.replaceAll("/", "\\");
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

.convert-container {
    display: flex;
    flex-direction: column;
    text-align: center;
    justify-content: center;
    margin: 20px auto;
    padding: 0 20px;
}

textarea {
  margin: 2px auto;
  width: 100%;
}

html {
  font-size: 14px;
  position: relative;
  min-height: 100%;
}

button.accept-policy {
  font-size: 1rem;
  line-height: inherit;
}

button {
  margin: 10px;
}
#newPath {
  height: 3rem;
}
#windowsLocation {
  font-size: 1.2rem;
}

#windowsLocation {
    word-break: break-all;
    word-wrap: break-word;
}

@media (min-width: 650px) {
    .convert-container {
        width: 100%;
    }
    #windowsLocation {
        word-break: normal;
        word-wrap: normal;
    }
    textarea {
    width: 50%;
    } 
}

@media (min-width: 768px) {
  html {
    font-size: 16px;
  }
  textarea {
    width: 40%;
    }
}
</style>