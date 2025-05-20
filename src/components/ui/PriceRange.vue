<template>
  <div
    class="bg-white rounded-[3.3rem] p-10 w-[320px] h-[320px] flex flex-col items-center justify-center"
  >
    <span class="text-sm font-semibold">Select the price</span>
    <div
      class="flex flex-col items-center gap-2 mt-4 border-[3px] border-[#E5E5EA] rounded-2xl overflow-hidden w-full"
    >
      <div class="flex items-center gap-4 bg-[#E5E5EA] p-3 py-5 relative w-full justify-between">
        <div
          :class="`absolute left-0 right-0 h-full rounded-r-2xl bg-white`"
          :style="`width: ${percentage}%`"
        ></div>
        <button
          @click="decrement"
          class="w-6 rounded-full flex items-center justify-center text-2xl font-bold z-10 text-[#3C3C43] cursor-pointer"
        >
          <svg class="w-full" viewBox="0 0 65 11" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path
              d="M5.29721 9.84051H27.6911H36.225H58.7399C61.2214 9.84051 63.0977 7.96426 63.0977 5.60382C63.0977 3.18286 61.2214 1.24609 58.7399 1.24609H36.225H27.6911H5.29721C2.87625 1.24609 1 3.18286 1 5.60382C1 7.96426 2.87625 9.84051 5.29721 9.84051Z"
              fill="#3C3C43"
              fill-opacity="0.36"
            />
            <path
              d="M58.7402 0.746094C61.5022 0.746251 63.5975 2.91122 63.5977 5.60352C63.5977 8.2492 61.4884 10.3407 58.7402 10.3408H5.29688C2.60459 10.3406 0.5 8.24462 0.5 5.60352C0.50016 2.91586 2.59093 0.746271 5.29688 0.746094H58.7402Z"
              stroke="#3C3C43"
              stroke-opacity="0.36"
            />
          </svg>
        </button>
        <div class="text-3xl font-semibold z-10">
          <span class="text-[#3C3C43]/50">$</span>{{ amount }}
        </div>
        <button
          class="w-6 h-12ounded-full flex items-center justify-center text-2xl font-bold z-10 text-[#3C3C43] cursor-pointer"
          @click="increment"
        >
          <svg class="w-full" viewBox="0 0 63 66" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path
              d="M35.225 61.5342C35.225 63.9551 33.2882 65.8314 30.9278 65.8314C28.5068 65.8314 26.6911 63.9551 26.6911 61.5342V36.8404H4.29721C1.87624 36.8404 0 34.9641 0 32.6037C0 30.1827 1.87624 28.246 4.29721 28.246H26.6911V5.00473C26.6911 2.58376 28.5068 0.70752 30.9278 0.70752C33.2882 0.70752 35.225 2.58376 35.225 5.00473V28.246H57.7399C60.2214 28.246 62.0977 30.1827 62.0977 32.6037C62.0977 34.9641 60.2214 36.8404 57.7399 36.8404H35.225V61.5342Z"
              fill="#3C3C43"
              fill-opacity="0.36"
            />
          </svg>
        </button>
      </div>
    </div>
    <div class="flex w-full justify-between text-black/30 text-sm mt-2">
      <span>${{ min }}</span>
      <span>${{ max }}</span>
    </div>
    {{ percentage }}
  </div>
</template>

<script lang="ts" setup>
import { ref, computed } from 'vue'
const amount = ref(56)

const min = 0
const max = 150

const increment = () => {
  if (amount.value < max) {
    amount.value++
  }
}
const decrement = () => {
  if (amount.value > min) {
    amount.value--
  }
}
//  percentage of the selected amount between the min and max
const percentage = computed(() => Math.floor((amount.value / max) * 100))
</script>

<style></style>
