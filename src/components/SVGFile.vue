<script setup lang="ts">
defineProps<{
  color: string
  backgroundColor: string
  svg: SVGElement
}>()
</script>

<template>
  <svg
    xmlns="http://www.w3.org/2000/svg"
    v-bind="svg.attributes"
    :fill="color"
    :background="backgroundColor"
    v-html="svg.innerHTML"
  ></svg>
</template>
