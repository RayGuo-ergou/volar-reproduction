<template>
  <CheckboxRoot
    v-bind="forwarded"
    v-model:checked="checked"
  >
    <CheckboxIndicator class="flex size-full items-center justify-center text-current">
      <slot>
        <IRmvInterfaceCheck class="size-4" />
      </slot>
    </CheckboxIndicator>
  </CheckboxRoot>
</template>

<script setup lang="ts">
import { CheckboxIndicator, CheckboxRoot, useForwardPropsEmits } from 'radix-vue';
import { CheckboxProps, CheckboxEmits } from './type.ts'

const props = defineProps<CheckboxProps>();
const emits = defineEmits<CheckboxEmits>();


// Both v-model="" and v-model:checked="" will work
const checked = defineModel<boolean>();

const forwarded = useForwardPropsEmits(props, emits);
</script>

