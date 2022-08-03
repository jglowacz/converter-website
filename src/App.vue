<script setup>
import { ref } from 'vue'
const temp = ref('')
const selected = ref('')


</script>

<template>
  <div id="main">
    <div class="degrees-container">
      <label class="label" for="degrees">Degrees:</label>
      <form>
        <input class="number-input" v-model="temp" type="number" pattern="[-60,212]">
      </form>
    </div>
    <div class="select-temp-container">
      <label for="select-temp">Type</label>
      <select class="select" v-model="selected" id="select-temp">
        <option disabled value="">Please select one</option>
        <option>Celsius</option>
        <option>Fahrenheit</option>
      </select>
    </div>
    <div class="temp-container">
      <div v-if="temp < -60 || temp > 212">Please enter correct value</div>
      <div v-else>
        <div v-if="selected === 'Celsius'">{{ temp }}°{{ selected.slice(0, 1) }} is {{ Math.round(temp * 9 / 5 + 32) /
            10
        }}°F
        </div>
        <div v-else-if="selected === 'Fahrenheit'">{{ temp }}°{{ selected.slice(0, 1) }} is {{ Math.round(temp - 32 * 5 /
            9
          ) / 10
        }}°C</div>
        <div v-else></div>
      </div>
    </div>
  </div>
</template>

<style scoped>
</style>
