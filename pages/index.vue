<template>
  <div>{{ data }}</div>
</template>

<script lang="ts">
import { defineComponent, useLazyAsyncData } from '#imports'

export default defineComponent({
  name: 'IndexPage',
  setup() {
    const { data } = useLazyAsyncData('index', () => {
      console.log('useLazyAsyncData')
      return Promise.resolve('data')
    })

    return { data }
  },
})
</script>
