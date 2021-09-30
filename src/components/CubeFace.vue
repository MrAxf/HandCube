<template>
  <div :class="['face', orientation]">
    <div :class="['sticker', color]"></div>
  </div>
</template>

<script setup>
import { computed, defineProps, reactive } from "vue";

defineProps({
  color: {
    validator(value) {
      return ['red', 'green', 'blue', 'yellow', 'orange', 'white'].includes(value)
    }
  },
  orientation: {
    required: true,
    validator(value) {
      return ['top', 'bottom', 'front', 'back', 'right', 'left'].includes(value)
    }
  },
});

</script>

<style scoped>
.face {
  position: absolute;
  width: 100px;
  height: 100px;
  background: black;
}
.face.front {
  transform: rotateY(0deg) translateZ(50px);
}
.face.right {
  transform: rotateY(90deg) translateZ(50px);
}
.face.back {
  transform: rotateY(180deg) translateZ(50px);
}
.face.left {
  transform: rotateY(-90deg) translateZ(50px);
}
.face.top {
  transform: rotateX(90deg) translateZ(50px);
}
.face.bottom {
  transform: rotateX(-90deg) translateZ(50px);
}

.face > .sticker {
  position: relative;
  width: 80px;
  height: 80px;
  margin: 10px;
  border-radius: 10px;
}
.face > .sticker.red {
  background: red;
}
.face > .sticker.blue {
  background: blue;
}
.face > .sticker.green {
  background: green;
}
.face > .sticker.yellow {
  background: yellow;
}
.face > .sticker.orange {
  background: orange;
}
.face > .sticker.white {
  background: white;
}
</style>
