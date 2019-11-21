<template>
  <div
    ref="resize"
    :style="computedHeightStyle"
  >
    <div :style="computedTransformStyle">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AutoResizeContainer',

  data() {
    return {
      scale: 1,
    }
  },
  computed: {
    computedHeightStyle() {
      return { height: 275 * this.scale + 'px' };
    },
    computedTransformStyle() {
      return {
        transform: `scale(${this.scale})`,
        transformOrigin: '0 0',
      };
    }
  },
  mounted() {
    window.addEventListener('resize', this.onResize);
    this.onResize();
  },
  destroyed() {
    window.removeEventListener('resize', this.onResize);
  },

  methods: {
    onResize() {
      const newScale = (this.$refs.resize.clientWidth / 1100).toFixed(2);
      if (this.scale !== newScale) {
        this.scale = newScale;
      }
    },
  }
}
</script>
