<template>
  <div>
    <div>
      <nuxt-link to="/hoge">to hoge</nuxt-link>
    </div>
    {{ data }}
  </div>
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

    console.log(data.value)

    return { data }
  },
})
</script>
