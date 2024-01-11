<script setup lang="ts">
import { ref } from 'vue'
import SVGFile from './SVGFile.vue'

withDefaults(
  defineProps<{
    color: string
    backgroundColor: string
  }>(),
  {
    color: '#000',
    backgroundColor: '#fff'
  }
)

const svg = ref<string | null>(null)

function loadSVG(event: Event) {
  const file = (event.target as HTMLInputElement).files?.[0]
  if (!file) return

  const reader = new FileReader()
  reader.onload = () => {
    // const parser = new DOMParser()
    // const doc = parser.parseFromString(reader.result as string, 'image/svg+xml')
    // svg.value = doc.querySelector('svg')
    // console.log(svg.value)
    svg.value = reader.result as string
  }
  reader.readAsText(file)
}
</script>

<template>
  <div>
    <input type="file" accept="image/svg+xml" @change="loadSVG" />
    <div
      class="logo"
      v-if="svg"
      v-html="svg"
      :style="{ fill: color, background: backgroundColor }"
    />
  </div>
</template>
