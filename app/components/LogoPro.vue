<script setup>
const colorMode = useColorMode()
</script>

<template>
  <div class="logo-container">
    <img
      :src="colorMode.value === 'dark' ? '/logos/aiden-logo.svg' : '/logos/aiden-logo-black.svg'"
      alt="Aiden"
      class="logo-image"
    >
  </div>
</template>

<style scoped>
.logo-container {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 60px;
  width: 200px;
}

.logo-image {
  max-height: 100%;
  max-width: 100%;
  object-fit: contain;
}
</style>
