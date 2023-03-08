<script setup lang="ts">
import { Proxy } from '~/composables/image'
</script>

<template>
  <RouterLink to="/foo" btn m-3>
    Go
  </RouterLink>
  <RouterLink to="/bar" btn m-3>
    Bar
  </RouterLink>
  <Proxy w-50 h-50 />
</template>
