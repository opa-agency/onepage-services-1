<template>
  <component
    :is="href ? 'a' : 'button'"
    :href="href"
    :class="[baseStyles, variantClasses]"
    v-bind="$attrs"
  >
    <slot />
  </component>
</template>

<script setup>
import { computed } from 'vue'
import clsx from 'clsx'

const props = defineProps({
  href: {
    type: String,
    default: undefined,
  },
  variant: {
    type: String,
    default: 'solid',
    validator: (value) => ['solid', 'outline'].includes(value),
  },
  color: {
    type: String,
    default: 'slate',
    validator: (value) => ['slate', 'blue', 'white'].includes(value),
  },
})

const baseStyles = 'group inline-flex items-center justify-center rounded-full py-2 px-4 text-sm font-semibold focus-visible:outline-2 focus-visible:outline-offset-2'

const solidVariantStyles = {
  slate:
    'bg-slate-900 text-white hover:bg-slate-700 hover:text-slate-100 active:bg-slate-800 active:text-slate-300 focus-visible:outline-slate-900',
  blue: 'bg-blue-600 text-white hover:text-slate-100 hover:bg-blue-500 active:bg-blue-800 active:text-blue-100 focus-visible:outline-blue-600',
  white:
    'bg-white text-slate-900 hover:bg-blue-50 active:bg-blue-200 active:text-slate-600 focus-visible:outline-white',
}

const outlineVariantStyles = {
  slate:
    'ring-1 ring-slate-200 text-slate-700 hover:text-slate-900 hover:ring-slate-300 active:bg-slate-100 active:text-slate-600 focus-visible:outline-blue-600 focus-visible:ring-slate-300',
  white:
    'ring-1 ring-slate-700 text-white hover:ring-slate-500 active:ring-slate-700 active:text-slate-400 focus-visible:outline-white',
}

const variantClasses = computed(() => {
  if (props.variant === 'outline') {
    return outlineVariantStyles[props.color] || ''
  }
  return solidVariantStyles[props.color] || ''
})
</script>
