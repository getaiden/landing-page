<script setup lang="ts">
// const columns = [{
//   label: 'Company',
//   children: [{
//     label: 'About'
//   }]
// }]

// const toast = useToast()

// const email = ref('')
// const loading = ref(false)

// function onSubmit() {
//   loading.value = true

//   toast.add({
//     title: 'Subscribed!',
//     description: 'You\'ve been subscribed to our newsletter.'
//   })
// }
</script>

<template>
  <USeparator
    class="h-px"
  />

  <UFooter :ui="{ top: 'border-b border-default' }">
    <!-- <template #top>
      <UContainer>
        <UFooterColumns :columns="columns">
        </UFooterColumns>
      </UContainer>
    </template> -->

    <template #left>
      <p class="text-sm text-muted">
        Copyright © {{ new Date().getFullYear() }}. All rights reserved.
      </p>
    </template>

    <template #right />
  </UFooter>
</template>
