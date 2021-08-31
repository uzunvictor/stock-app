<script lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import { defineComponent } from '@vue/runtime-core'
import Stock from './components/Stock.vue'

export default defineComponent({
  name: 'App',
  components: { Stock}
})
</script>

<template>
<div class="container">
  <div class="title">
    <h2>Stock Page</h2>
    <Stock />
  </div>
</div>
</template>

