<script setup lang="ts">
const model = defineModel<boolean>()

const icon = computed(() => {
  return model.value ? 'i-heroicons-x-mark-16-solid' : 'i-heroicons-bars-3-bottom-left-16-solid'
})

function onOpen() {
  model.value = !model.value
}
</script>

<template>
  <header class="bg-white/75 dark:bg-gray-950/75 backdrop-blur border-b -mb-px sticky top-0 z-50 border-gray-200 dark:border-gray-800">
    <div class="mx-auto px-4 sm:px-6 lg:px-8 max-w-7xl flex items-center justify-between gap-3 h-[--header-height]">
      <div class="lg:flex-1 flex items-center gap-1.5 min-w-0">
        <span>Logo Text</span>
      </div>

      <ul class="items-center gap-x-8 hidden lg:flex">
        <li class="relative"><a class="text-sm/6 font-semibold flex items-center gap-1 text-primary">Docs</a></li>
        <li class="relative"><a class="text-sm/6 font-semibold flex items-center gap-1 hover:text-primary">Pro</a></li>
        <li class="relative"><a class="text-sm/6 font-semibold flex items-center gap-1 hover:text-primary">Pricing</a></li>
        <li class="relative"><a class="text-sm/6 font-semibold flex items-center gap-1 hover:text-primary">Templates</a></li>
        <li class="relative"><a class="text-sm/6 font-semibold flex items-center gap-1 hover:text-primary">Releases</a></li>
      </ul>

      <div class="flex items-center justify-end lg:flex-1 gap-1.5">
        <UButton color="gray">Log in</UButton>
        <UButton variant="outline">Sign Up</UButton>
        <UButton class="lg:hidden" :icon="icon" square variant="ghost" @click="onOpen"></UButton>
      </div>
    </div>
  </header>
</template>
