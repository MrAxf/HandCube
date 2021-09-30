<template>
  <div class="viewport">
    <div class="rubiks-cube">
      <CubePiece :face-right="true" :translate-x="100" />
      <CubePiece :face-left="true" :translate-x="-100" />
      <CubePiece :face-front="true" :translate-z="100" />
      <CubePiece :face-back="true" :translate-z="-100" />
      <CubePiece :face-front="true" :face-right="true" :translate-x="100" :translate-z="100" />
      <CubePiece :face-back="true" :face-right="true" :translate-x="100" :translate-z="-100" />
      <CubePiece :face-back="true" :face-left="true" :translate-x="-100" :translate-z="-100" />
      <CubePiece :face-front="true" :face-left="true" :translate-x="-100" :translate-z="100" />

      <CubePiece :face-bottom="true" :translate-y="100" />
      <CubePiece :face-bottom="true" :face-right="true" :translate-x="100" :translate-y="100" />
      <CubePiece :face-bottom="true" :face-left="true" :translate-x="-100" :translate-y="100" />
      <CubePiece :face-bottom="true" :face-front="true" :translate-y="100" :translate-z="100" />
      <CubePiece :face-bottom="true" :face-back="true" :translate-y="100" :translate-z="-100" />
      <CubePiece :face-bottom="true" :face-front="true" :face-right="true" :translate-x="100" :translate-y="100" :translate-z="100" />
      <CubePiece :face-bottom="true" :face-back="true" :face-right="true" :translate-x="100" :translate-y="100" :translate-z="-100" />
      <CubePiece :face-bottom="true" :face-front="true" :face-left="true" :translate-x="-100" :translate-y="100" :translate-z="100" />
      <CubePiece :face-bottom="true" :face-back="true" :face-left="true" :translate-x="-100" :translate-y="100" :translate-z="-100" />

      <CubePiece :face-top="true" :translate-y="-100" />
      <CubePiece :face-top="true" :face-right="true" :translate-x="100" :translate-y="-100" />
      <CubePiece :face-top="true" :face-left="true" :translate-x="-100" :translate-y="-100" />
      <CubePiece :face-top="true" :face-front="true" :translate-y="-100" :translate-z="100" />
      <CubePiece :face-top="true" :face-back="true" :translate-y="-100" :translate-z="-100" />
      <CubePiece :face-top="true" :face-front="true" :face-right="true" :translate-x="100" :translate-y="-100" :translate-z="100" />
      <CubePiece :face-top="true" :face-back="true" :face-right="true" :translate-x="100" :translate-y="-100" :translate-z="-100" />
      <CubePiece :face-top="true" :face-front="true" :face-left="true" :translate-x="-100" :translate-y="-100" :translate-z="100" />
      <CubePiece :face-top="true" :face-back="true" :face-left="true" :translate-x="-100" :translate-y="-100" :translate-z="-100" />
    </div>
  </div>
</template>

<script setup>
import CubePiece from './components/CubePiece.vue'

// This starter template is using Vue 3 experimental <script setup> SFCs
// Check out https://github.com/vuejs/rfcs/blob/master/active-rfcs/0040-script-setup.md
</script>

<style>
#app {
  width: 100%;
  height: 100%;
}
.viewport {
  width: 100%;
  height: 100%;
  perspective: 600px;
}
.rubiks-cube {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 300px;
  height: 300px;
  margin: 0;
  transform-style: preserve-3d;
  transform: translate(-50%, -50%) rotateX(-30deg) rotateY(45deg);
  /* transform: rotateX(-30deg) rotateY(45deg) translate(50%, 50%); */
}
</style>
