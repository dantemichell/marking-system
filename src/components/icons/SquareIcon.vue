<template>
    <svg width="100%" height="100%" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
        <rect x="4" y="4" width="16" height="16" :fill="color" />
    </svg>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';

export default defineComponent({
  name: 'SquareIcon',
  props: {
    color: {
      type: String as PropType<string>,
      default: 'black'
    }
  }
});
</script>