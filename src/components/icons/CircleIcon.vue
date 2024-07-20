<template>
    <svg width="100%" height="100%" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
        <circle cx="12" cy="12" r="10"  :fill="color" />
    </svg>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';

export default defineComponent({
  name: 'CircleIcon',
  props: {
    color: {
      type: String as PropType<string>,
      default: 'black'
    }
  }
});
</script>