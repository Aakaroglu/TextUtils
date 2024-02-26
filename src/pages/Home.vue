<script setup>
import { inject, ref } from "vue";

    const content = ref('');
    const darkMode = inject("darkMode");
    
    const ConvertToUpperCase = () => {
        content.value = content.value.split(" ").map((c) => c.
        toUpperCase()).join(" ");
    }
    const lowerCase = () => {
        content.value = content.value.split(" ").map((c) => c.
        toLowerCase()).join(" ");
    }
    const clear = () => {
        content.value = '';
    }
    const CopyToClipBoard = () => {
        navigator.clipboard.writeText(content.value);
    }
    const RemoveExtraSpace = () => {
        content.value = content.value.split(/[ ]+/).join(" ");
    }




</script>
<template>
    <div class="container" :class="darkMode?'text-white':'text-dark'">
      <div class="container my-3">
        <h1>Enter the text to analyze below</h1>
        <textarea
          class="form-control"
          v-model="content"
          name=""
          id=""
          cols="30"
          rows="8"
        ></textarea>
        <div class="my-3">
            <button @click="ConvertToUpperCase" class="btn btn-primary mx-1">Convert to UpperCase</button>
            <button @click="lowerCase" class="btn btn-primary mx-1">Convert to LowerCase</button>
            <button @click="clear" class="btn btn-primary mx-1">Clear Text</button>
            <button @click="CopyToClipBoard" class="btn btn-primary mx-1">Copy Text</button>
            <button @click="RemoveExtraSpace" class="btn btn-primary mx-1">Remove Extra Space</button>


        </div>
      </div>
      <div class="container my-3">
        <h2 class="h2">Your Text Summary</h2>
        <p>{{ content.split(" ").length }} words and {{content.length}} Characters</p>
        <p>{{ content.split(" ").length*0.008 }} Minutes read</p>
        <h2 class="h2">Preview</h2>
        <p v-if="content.length<1">Enter Something in the TextBox above to preview it here</p>
        <p v-else>{{ content }}</p>
      </div>
    </div>
  </template>
  

  
  <style scoped>
  /* İsteğe bağlı stiller */
  </style>
  