<template>
  <div>
    <UContainer class="pt-6 pb-10 md:pt-10 md:pb-16 max-w-5xl mx-auto">
      <UPageHeader
        title="Contact Us"
        description="Have questions or feedback? We'd love to hear from you."
        class="mb-4"
      />

      <div class="w-full h-[calc(100vh-150px)] min-h-[900px] bg-white dark:bg-gray-900 rounded-lg overflow-hidden shadow-sm">
        <iframe
          data-tally-src="https://tally.so/r/nrpYOl?transparentBackground=1"
          width="100%"
          height="100%"
          frameborder="0"
          marginheight="0"
          marginwidth="0"
          title="Contact us"
          class="tally-iframe"
        />
      </div>
    </UContainer>
  </div>
</template>

<script setup lang="ts">
import { onMounted, useHead } from '#imports'

useHead({
  title: 'Contact Us',
  meta: [
    { name: 'description', content: 'Contact us for any questions or feedback about our services.' }
  ]
})

onMounted(() => {
  // Load Tally script
  if (!document.querySelector('script[src="https://tally.so/widgets/embed.js"]')) {
    const script = document.createElement('script')
    script.src = 'https://tally.so/widgets/embed.js'
    script.async = true
    document.head.appendChild(script)
  }
})
</script>

<style>
.tally-iframe {
  border: 0;
  height: 100%;
  width: 100%;
}

/* Ensure form is responsive on all devices */
@media (max-width: 768px) {
  .tally-iframe {
    min-height: 1000px; /* Increase height on mobile */
  }
}
</style>
