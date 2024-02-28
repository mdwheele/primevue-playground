<script setup>
import { onMounted, inject, useSlots } from 'vue'

const props = defineProps({
  value: [String, Object, Number, Boolean]
})

const slots = useSlots()

const api = inject('dropdown')

onMounted(() => {
  const label = slots.default()[0].children

  if (api.register) {
    api.register({ label, value: props.value })
  }
})
</script>

<template>

</template>
