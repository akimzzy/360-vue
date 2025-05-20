<script setup lang="ts">
import FlightDetails from './components/ui/FlightDetails.vue'
import PumpFill from './components/ui/PumpFill.vue'
import TranslateLanguage from './components/ui/TranslateLanguage.vue'
import PriceRange from './components/ui/PriceRange.vue'
</script>

<template>
  <div class="flex h-full gap-8 flex-wrap bg-gray-100 p-10">
    <FlightDetails />
    <PumpFill />
    <TranslateLanguage />
    <PriceRange />
  </div>
</template>
