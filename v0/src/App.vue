<template>
  <div>
    <h1>Vuetify0 Starter</h1>
    <p>
      Current theme: {{ theme.selectedId }}
    </p>
    <button @click="toggleTheme">Toggle theme</button>
  </div>
</template>

<script setup lang="ts">
  import { useTheme } from '@vuetify/v0'

  const theme = useTheme()

  function toggleTheme () {
    theme.cycle()
  }
</script>
