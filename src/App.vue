<!-- Your UI should include the following elements:

Text input for the user's URL
"Shorten" button to trigger the link shortening
Display area to return the shortened URL to the user -->

<script setup>
import { ref } from 'vue'
function shortenURL(url) {

}
const selected = ref('')
</script>

<template>
  <div id="main">
    <form>
      <label for="degrees">Degrees:</label><br>
      <input type="number" id="degrees" name="degrees-input">
    </form>
    <div>Selected: {{ selected }}</div>
    <select v-model="selected">
      <option value="" disabled>Please select one</option>
      <option>Celsius</option>
      <option>Fahrenheit</option>
    </select>
  </div>
</template>

<style scoped>
</style>
