<template lang="pug">
.page
  p this is index page
  p {{msg}}
  p {{state.count}}
  p {{state.double}}
  .btn(@click="increment") button
</template>

<script>
import { reactive, computed } from 'vue'
import consola from 'consola'

export default {
  data() {
    return {
      msg: 'ok'
    }
  },
  setup() {
    consola.info("info")
    consola.success("success")
    consola.error("error")
    const state = reactive({
      count: 0,
      double: computed(() => state.count * 2)
    })
    function increment() {
      state.count++
    }

    return {
      state,
      increment
    }
  }
}
</script>
