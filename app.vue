<script setup lang="ts">

const isOpen = ref(false)

const links = [
  [{
    label: 'Profile',
    avatar: {
      src: 'https://avatars.githubusercontent.com/u/739984?v=4'
    },
    badge: 100
  }, {
    label: 'Installation',
    icon: 'i-heroicons-home',
    to: '/getting-started/installation'
  }, {
    label: 'Vertical Navigation',
    icon: 'i-heroicons-chart-bar',
    to: '/components/vertical-navigation'
  }, {
    label: 'Command Palette',
    icon: 'i-heroicons-command-line',
    to: '/components/command-palette'
  }], [{
    label: 'Examples',
    icon: 'i-heroicons-light-bulb'
  }, {
    label: 'Help',
    icon: 'i-heroicons-question-mark-circle'
  }]
]

for (let i=0; i<20; ++i) {
  links[0].push({
    label: `Mock Item ${i+1}`,
    icon: 'i-heroicons-star',
    to: '#'
  })
}
</script>

<template>
  <!-- Header -->
  <Header v-model="isOpen"></Header>

  <main class="min-h-[calc(100vh-var(--header-height))]">
    <div class="mx-auto px-4 sm:px-6 lg:px-8 max-w-7xl">
      <div class="flex flex-col lg:grid lg:grid-cols-10 lg:gap-8">
        <!-- Sidebar -->
        <div class="lg:col-span-2">
          <aside class="hidden overflow-y-auto lg:block lg:max-h-[calc(100vh-var(--header-height))] lg:sticky lg:top-[--header-height] py-8 lg:px-4 lg:-mx-4">
            <div class="relative">
              <UVerticalNavigation :links="links" />
            </div>
          </aside>
        </div>

        <!-- Main Content -->
        <div class="lg:col-span-8">
          <div class="py-8">
            <h1>Main Content Area</h1>
            <p v-for="n in 100">This is an example content area. You can add more sections or features here.</p>
          </div>
        </div>
      </div>
    </div>
  </main>

  <UModal v-model="isOpen" fullscreen :transition="false" :overlay="false" :ui="{ background: 'bg-white dark:bg-gray-950' }">
    <!-- Header -->
    <Header v-model="isOpen"></Header>

    <div class="py-4 overflow-y-auto">
      <div class="relative">
        <UVerticalNavigation :links="links" />
      </div>
    </div>
  </UModal>

</template>
