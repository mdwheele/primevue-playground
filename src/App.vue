<script setup>
import { Dropdown, Option } from '@/components'
import { ref } from 'vue'

const value = ref(null)
</script>

<template>
  <div class="h-screen flex flex-col gap-12 items-center justify-center bg-gradient-to-tr from-fuchsia-700 to-purple-700">
    <Dropdown v-model="value">
      <Option :value="true">True</Option>
      <Option :value="false">False</Option>
    </Dropdown>

    <pre>{{ value }}</pre>
  </div>
</template>
