<script setup lang="ts">
definePageMeta({
  layout: "default",
});
const { app } = useAppConfig()
const localPath = useLocalePath()
const FEATURES = app.features;
</script>
<template>
  <div>
    <div class="p-4 h-screen flex flex-col justify-center items-center">
      <div class="grid grid-cols-[1fr,40%] gap-8 w-full content-center">
        <div class="flex flex-col justify-between items-center">
          <div class="w-[60%]">
            <h1 class="text-4xl font-bold">{{ $t('welcome.title') }} <span class="text-green-500 font-black">Nuxt Boilerplate!</span></h1>
            <p>{{ $t('welcome.subTitle') }}</p>
            <UButton class="mt-2" :to="localPath('get-started')">{{ $t('welcome.getStarted') }}</UButton>
            <p class="my-4">{{ $t('welcome.description') }}</p>
            <div class="grid grid-cols-4 gap-4 mt-6 content-center align-center">
              <div
                  v-for="(item, index) in FEATURES"
                  :key="index"
                  class="flex flex-col justify-center items-center bg-white/20 shadow-lg ring-1 ring-black/5 h-[100px] rounded-2xl transition duration-600 opacity-50 cursor-pointer hover:opacity-100 hover:shadow-white-100/10 hover:shadow-2xl"
              >
                <UIcon :name="item.icon" size="32" />
                <div>{{ item.label }}</div>
              </div>
            </div>
          </div>
        </div>
        <div class="flex flex-col justify-between items-center self-center">
          <div
              class="relative h-[200px] w-[200px] flex flex-col justify-center items-center"
          >
            <div
                class="absolute bg-green-500/30 filter blur-2xl w-[300px] h-[300px] rounded-full animate animate-pulse"
            />
            <UIcon
                name="simple-icons:nuxt"
                class="relative z-1 text-[180px] text-white"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>