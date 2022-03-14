<template>
  <div></div>
</template>

<script>
import WaveSurfer from "wavesurfer.js";
export default {
  props: ['src', 'options'],
  data() {
    return {
      publicWaveSurfer: {}
    };
  },
  mounted() {
    let options = this.options;
    let wsOptions = Object.assign({ container: this.$el }, options);
    this.publicWaveSurfer = new WaveSurfer.create(wsOptions);
    this.publicWaveSurfer.load(this.src);
  },
  beforeDestroy() {
    this.publicWaveSurfer.destroy();
  }
};
</script>

<style lang="css" scoped>
div {
  position: relative;
}
</style>
