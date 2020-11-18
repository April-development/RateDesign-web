<template>
  <div>
    <nuxt-link to="/admin"><Button>Жми меня</Button></nuxt-link>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { Button } from 'ant-design-vue'

export default Vue.extend({
  components: {
    Button,
  },
})
</script>
