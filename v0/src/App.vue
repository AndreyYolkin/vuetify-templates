<template>
  <div class="container mx-auto">
    <h1>Vuetify0 Starter</h1>
    <p>
      Current theme: {{ selected }}
    </p>
    <Selection.Root v-model="selected" mandatory="force">
      <div class="flex flex-col gap-2">
        <Selection.Item
          v-for="item in ['light', 'dark']"
          :key="item"
          :value="item"
        >
          <template #default="{ isSelected, select }">
            <button
              class="px-3 py-1.5 border rounded text-left text-sm bg-surface"
              :class="isSelected ? 'border-primary' : 'border-divider'"
              @click="select"
            >
              {{ item }}
            </button>
          </template>
        </Selection.Item>
      </div>
    </Selection.Root>
  </div>
</template>

<script setup lang="ts">
  import { Selection, useTheme } from '@vuetify/v0'
  import { computed } from 'vue'

  const theme = useTheme()

  const selected = computed({
    get () {
      return theme.selectedId.value
    },
    set (value) {
      theme.select(value!)
    },
  })
</script>
