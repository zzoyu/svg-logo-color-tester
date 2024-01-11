<script setup lang="ts">
import { ref } from 'vue'
import SVGLoader from './components/SVGLoader.vue'

const color = ref('#000')
const backgroundColor = ref('#fff')
</script>

<template>
  <header>
    <h1>SVG Logo Color Simple Tester</h1>
    <p>fill 설정이 되어있는 SVG에는 동작 안 함</p>
  </header>

  <main>
    <div>
      <label for="color"
        >Color <input type="color" v-model="color" />
        <input type="text" v-model="color" />
      </label>
      <br />
      <label for="backgroundColor"
        >Background Color <input type="color" v-model="backgroundColor" />
        <input type="text" v-model="backgroundColor" />
      </label>
    </div>

    <br />

    <SVGLoader :color="color" :background-color="backgroundColor" />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}
</style>
