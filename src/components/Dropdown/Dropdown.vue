<script setup>
import Dropdown from 'primevue/dropdown'
import { provide, ref } from 'vue'

const props = defineProps({
  modelValue: [String, Object, Number, Boolean]
})

defineEmits(['update:model-value'])

const options = ref([])

function register(option) {
  options.value.push(option)
}

provide('dropdown', {
  register,
})
</script>

<template>
  <Dropdown 
    :model-value="modelValue" 
    @update:model-value="$emit('update:model-value', $event)" 
    :options="options" 
    option-label="label" 
    option-value="value"
    placeholder="PrimeVue is awesome?" 
  />

  <slot/>
</template>