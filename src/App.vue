<template>
  <router-view></router-view>
</template>

<script>
import {ref, provide} from 'vue'
import {router} from './router/router'


export default {
  name: 'App',
  setup() {
    const width = document.documentElement.clientWidth
    const menuVisible = ref(width > 500)
    provide('xxx', menuVisible)
    router.afterEach(() => {
      if (width <= 500) {
        menuVisible.value = false
      }
    })

  }
}
</script>

