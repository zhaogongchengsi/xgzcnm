<script setup lang="ts">
const TIME = ref(new Date(2023, 7, 24)) // 2023-8-24

const currentDate = new Date()
const timeDiff = currentDate.getTime() - unref(TIME).getTime()
// const second = ref(Math.floor(timeDiff / 1000) % 60)
// const minute = ref(Math.floor(timeDiff / (1000 * 60)) % 60)
// const hour = ref(Math.floor(timeDiff / (1000 * 60 * 60)) % 24)

const day = computed(() => {
  const day = Math.floor(timeDiff / (1000 * 60 * 60 * 24))
  const month = Math.floor(day / 30.44)
  const year = Math.floor(month / 12)

  return {
    day,
    month,
    year,
  }
})
</script>

<template>
  <div
    class="flex flex-col items-center gap-10 text-5 leading-6 lg:text-8 md:text-7 sm:text-6 xl:text-9 md:leading-none"
  >
    <span class="whitespace-pre-line">{{ $t('content') }}</span>
    <h2 class="flex items-center gap-2 border border-color-red-600 rounded-md px-3 py-2 text-red-700">
      <Time> {{ day.year }} </Time>
      <Space />
      <Time> {{ day.month }} </Time>
      <Space />
      <Time> {{ day.day }} </Time>
    </h2>
  </div>
</template>
