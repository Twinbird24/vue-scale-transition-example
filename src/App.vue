<template>
  <auto-resize-container>
    <Blocks />
  </auto-resize-container>
</template>

<script>
import Blocks from './Blocks';
import AutoResizeContainer from './AutoResizeContainer';

export default {
  components: {
    Blocks,
    AutoResizeContainer
  },

  name: 'app',
}
</script>