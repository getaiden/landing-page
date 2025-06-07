<script setup>
const colorMode = useColorMode()

// Force the component to be client-side only to ensure proper theme detection
const mounted = ref(false)
onMounted(() => {
  mounted.value = true
})
</script>

<template>
  <div class="logo-container">
    <ClientOnly>
      <img
        v-if="mounted"
        :src="colorMode.value === 'dark' ? '/logos/aiden-logo.svg' : '/logos/aiden-logo-black.svg'"
        alt="Aiden"
        class="logo-image"
      >
      <template #fallback>
        <img
          src="/logos/aiden-logo.svg"
          alt="Aiden"
          class="logo-image"
        >
      </template>
    </ClientOnly>
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
