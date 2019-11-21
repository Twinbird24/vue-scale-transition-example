<template>
  <div class="container">
    <transition name="fade">
      <div
        class="block"
        id="block_1"
        v-show="blockToggle"
      />
    </transition>
    <transition name="fade">
      <div
        class="block"
        id="block_2"
        v-show="!blockToggle"
      />
    </transition>
    <div class="textblock">This is another div</div>
  </div>
</template>

<script>

export default {
  name: 'Blocks',

  data() {
    return {
      blockToggle: false,
    }
  },

  mounted() {
    this.fadeBlock();
  },

  methods: {
    fadeBlock() {
      setTimeout(() => {
        this.blockToggle = !this.blockToggle;
        this.fadeBlock();
      }, 1000);
    },
  }
}
</script>

<style>
.container {
  position: relative;
  overflow: hidden;
  height: 275px;
  width: 1100px;
  transform-origin: 0;
  /* ##### Increasing the scale here (i.e. from 1.00 to 1.07) will break the z-index ##### */
  transform: scale(1.00);
}

#block_1 {
  background-color: #9999ff;
}

#block_2 {
  background-color: #6666ff;
}

.block {
  width: 100%;
  height: 100%;
}

.textblock {
  background-color: white;
  position: absolute;
  bottom: 0;
  z-index: 99;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 1s ease;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
  z-index: 1;
  position: absolute;
  top: 0;
  left: 0;
}
.fade-enter-to,
.fade-leave {
  opacity: 1;
  z-index: 2;
  position: static;
}
</style>
