<script setup lang="ts">
import { matedData, proxyEl } from '~/composables/floating'
const attr = useAttrs()
matedData.attrs = attr
const el = ref()
onMounted(() => {
  proxyEl.value = el.value
})
</script>

<template>
  <div ref="el" bg-gray-500 />
</template>
