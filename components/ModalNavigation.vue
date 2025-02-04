<script setup lang="ts">
import type { VerticalNavigationLink } from '#ui/types'
const model = defineModel<boolean>()

const props = defineProps<{
  links?: VerticalNavigationLink[] | VerticalNavigationLink[][]
}>()
</script>

<template>
  <UModal v-model="model" fullscreen :transition="false" :overlay="false" :ui="{ background: 'bg-white dark:bg-gray-950' }">
    <!-- Header -->
    <Header v-model="model"></Header>

    <div class="py-4 overflow-y-auto">
      <div class="relative">
        <UVerticalNavigation :links="links" />
      </div>
    </div>
  </UModal>
</template>
