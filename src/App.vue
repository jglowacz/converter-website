<script setup>
import { ref } from 'vue'
const temp = ref('')
const selected = ref('')
</script>

<template>
  <div id="main">
    <div class="degrees-container">
      <label for="degrees">Degrees:</label>
      <form>
        <input v-model="temp" type="number">
      </form>
    </div>
    <div class="select-temp-container">
      <label for="select-temp">Type</label>
      <select v-model="selected" id="select-temp">
        <option disabled value="">Please select one</option>
        <option>Celsius</option>
        <option>Fahrenheit</option>
      </select>
    </div>
    <div v-if="selected === 'Celsius'">{{ temp }}°{{ selected.slice(0, 1) }} is {{ Math.round(temp * 9 / 5 + 32) }}°F
    </div>
    <div v-else-if="selected === 'Fahrenheit'">{{ temp }}°{{ selected.slice(0, 1) }} is {{ Math.round(temp - 32 * 5 / 9
      )
    }}°C</div>
    <div v-else></div>
  </div>
</template>

<style scoped>
</style>
