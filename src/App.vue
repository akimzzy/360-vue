<script setup lang="ts">
import FlightDetails from './components/ui/FlightDetails.vue'
import PumpFill from './components/ui/PumpFill.vue'
import TranslateLanguage from './components/ui/TranslateLanguage.vue'
</script>

<template>
  <div class="flex h-full gap-8 flex-wrap">
    <FlightDetails />
    <PumpFill />
    <TranslateLanguage />
  </div>
</template>

<style scoped></style>
