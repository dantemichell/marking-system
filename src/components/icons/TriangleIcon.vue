<template>
    <svg width="100%" height="100%" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M12 2l10 18H2L12 2z" :fill="color" />
    </svg>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';

export default defineComponent({
  name: 'TriangleIcon',
  props: {
    color: {
      type: String as PropType<string>,
      default: 'black'
    }
  }
});
</script>