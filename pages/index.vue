<script lang="ts" setup>
import init, { pulldown_cmark } from '@/@markdown-wasm/hello_wasm'
import { useState } from 'nuxt/app'

definePageMeta({ layout: 'custom' })

// WASM
const isWasmLoading = useState('isWasmLoading', () => false)
init().then(() => (isWasmLoading.value = true))

const textValue = useState<string>('textValue')

const convertedHTML = computed<string>(() => {
  if (!isWasmLoading.value) return ''
  return pulldown_cmark(textValue.value)
})
</script>

<template>
  <div class="flex flex-col gap-8 h-full">
    <h1 class="text-4xl text-bold">Markdown Converter</h1>
    <div class="flex gap-16 flex-1">
      <div class="flex-1 flex flex-col gap-2">
        <p class="text-lg">markdown</p>
        <textarea name="value" v-model="textValue" class="textarea textarea-bordered w-full h-full"></textarea>
      </div>
      <div class="flex-1 flex flex-col gap-2 h-full cursor-not-allowed">
        <p class="text-lg">HTML</p>
        <div v-html="convertedHTML" class="border rounded-[8px] px-4 py-2 h-full overflow-auto"></div>
      </div>
    </div>
  </div>
</template>
