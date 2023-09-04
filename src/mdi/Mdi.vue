<template>
  <link
    rel="stylesheet"
    href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@24,400,0,0"
  />
  <span class="material-icons icon md-48">
    {{ props.icon }}
  </span>
</template>

<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps({
  icon: { type: String, required: true },
  width: { type: [String, Number], default: 30 },
  height: { type: [String, Number], default: 30 },
  size: { type: Number, default: 24 }
})

const iconWidth = computed(() => {
  const width = props.width
  return typeof width === 'number' ? `${width}px` : width
})

const iconHeight = computed(() => {
  const height = props.height
  return typeof height === 'number' ? `${height}px` : height
})
</script>
<style scoped>
.material-icons {
  font-size: v-bind('`${props.size}px`');
  font-variation-settings:
    'FILL' 1,
    'wght' 400,
    'GRAD' 0,
    'opsz' 24;
}
</style>
