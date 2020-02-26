<template>
  <div>
    {{ message }}
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  data () {
    const message: Foo = 'test'

    return {
      message
    }
  }
})
</script>
