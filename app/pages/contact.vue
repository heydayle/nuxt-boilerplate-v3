<script setup lang="ts">
useHead({
  title: 'Contact',
  meta: [
    {
      name: 'description',
      content: 'Contact us for more information or support.'
    }
  ]
})
const config = useAppConfig()
const contacts = computed(() => config.app.contacts)
</script>

<template>
  <div class="container flex flex-col items-center justify-center min-h-[calc(100vh-10rem)]"> 
    <div>
      <div class="relative">
        <div class="absolute left-1/2 -top-[10%] z-[-1] transform -translate-x-1/2 -translate-y-1/4 bg-green-500/50 filter blur-3xl w-[500px] h-[500px] rounded-full" />
        <NuxtImg src="/images/logo.png" alt="Devaloka Logo" class="mx-auto mb-4 w-32 h-32" />
        <div>
          <h1 class="text-3xl font-bold text-center mb-2">{{ config.app.meta.title }}</h1>
        </div>
      </div>
      <ul class="flex space-x-4 justify-center items-center mt-4">
        <li v-for="(item, index) in contacts" :key="index">
          <ULink as="a" :to="item.href" class="inline-flex items-center space-x-1 ring-1 ring-primary-200 rounded-md px-2 py-1 transition-colors">
            <UIcon :name="item.icon" />
            <span>{{ item.name }}</span>
          </ULink>
        </li>
      </ul>
    </div>
    <div class="mt-8">
      <iframe src="https://github.com/sponsors/heydayle/card" title="Sponsor heydayle" height="90" width="600" style="border: 1px solid var(--ui-border-muted);border-radius: 12px;background-color: transparent;"/>
    </div>
  </div>
</template>

<style scoped>

</style>