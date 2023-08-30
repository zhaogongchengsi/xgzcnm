<script setup lang="ts">
const { locale } = useI18n()
</script>

<template>
  <header class="mx-auto flex items-center justify-between gap-3 px-3 py-4 container md:px-0">
    <div class="flex items-center gap-4">
      <h1 class="h-6 w-6">
        <NuxtLink to="/">
          <img src="/logo.svg" alt="logo">
        </NuxtLink>
      </h1>
      <select v-model="locale" class="rounded bg-transparent px-2 py-1 text-emerald outline-none">
        <option value="en">
          English
        </option>
        <option value="cn">
          中文
        </option>
      </select>
    </div>

    <DarkToggle />
  </header>
  <main class="mx-auto w-full flex flex-1 items-center justify-center px-3 container md:px-0">
    <slot />
  </main>
</template>
