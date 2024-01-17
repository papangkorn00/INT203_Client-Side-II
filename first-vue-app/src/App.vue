<script setup>
import {ref} from "vue"

const count = ref(0)
const isDark = ref(false)

const decreaseCount = () => {
  return count.value === 0 ? count.value : --count.value
}

const increaseCount = () => {
  return ++count.value
}
</script>

<template>
  <div class="min-h-screen" :class="isDark ? 'bg-black' : 'bg-white'">
    <div class="flex justify-end">
      <input
        type="checkbox"
        class="toggle my-6 mr-5"
        v-model="isDark"
        @click="!isDark"
      />
    </div>

    <div class="flex justify-evenly">
      <button class="p-5 btn btn-success" @click="decreaseCount">-</button>
      <h1 class="text-lg font-medium">Counter : {{ count }}</h1>
      <button class="p-5 btn btn-success" @click="increaseCount">+</button>
    </div>
  </div>
</template>
