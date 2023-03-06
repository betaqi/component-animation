<template>
  <main font-sans text="center gray-700 dark:gray-200">
    <RouterView />
    <TheImgContainer v-slot="Props">
      <TheImage v-bind="Props" />
    </TheImgContainer>
  </main>
</template>
