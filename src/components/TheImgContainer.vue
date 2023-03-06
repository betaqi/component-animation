<script setup lang="ts">
import type { StyleValue } from '@vue/runtime-dom'
import { proxyEl } from '~/composables/floating'
const observerOptions = {
  childList: true,
  attributes: true,
  subtree: true,
}

const rect = ref<DOMRect | undefined>()
const Style = computed((): StyleValue => ({
  position: 'fixed',
  transition: 'all .1s',
  top: `${rect.value?.top ?? 0}px`,
  left: `${rect.value?.left ?? 0}px`,
}),
)

const observer = new MutationObserver((mutations) => {
  const element = mutations[0].target as Element
  rect.value = element.getBoundingClientRect()
})

function update() {
  rect.value = proxyEl.value?.getBoundingClientRect()
  proxyEl.value && observer.observe(proxyEl.value, observerOptions)
}

window.addEventListener('resize', update)
watchEffect(update)
</script>

<template>
  <div :style="Style">
    <slot v-bind="matedData.attrs" />
  </div>
</template>
