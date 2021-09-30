<template>
    <div class="cube" :style="transform">
        <CubeFace :color="faceTop ? 'green' : undefined" orientation="top" />
        <CubeFace :color="faceBottom ? 'blue' : undefined" orientation="bottom" />
        <CubeFace :color="faceFront ? 'red' : undefined" orientation="front" />
        <CubeFace :color="faceBack ? 'orange' : undefined" orientation="back" />
        <CubeFace :color="faceLeft ? 'yellow' : undefined" orientation="left" />
        <CubeFace :color="faceRight ? 'white' : undefined" orientation="right" />
    </div>
</template>

<script setup>
import { computed, defineProps, reactive } from "vue";
import CubeFace from './CubeFace.vue'

const props = defineProps({
    translateX: {
        type: Number,
        default: 0,
    },
    translateY: {
        type: Number,
        default: 0,
    },
    translateZ: {
        type: Number,
        default: 0,
    },
    rotateX: {
        type: Number,
        default: 0,
    },
    rotateY: {
        type: Number,
        default: 0,
    },
    rotateZ: {
        type: Number,
        default: 0,
    },
    faceTop: {
        type: Boolean,
        default: false,
    },
    faceBottom: {
        type: Boolean,
        default: false,
    },
    faceFront: {
        type: Boolean,
        default: false,
    },
    faceBack: {
        type: Boolean,
        default: false,
    },
    faceLeft: {
        type: Boolean,
        default: false,
    },
    faceRight: {
        type: Boolean,
        default: false,
    }
});

const transform = computed(() => `transform: translate(-50%, -50%) rotateX(${props.rotateX}deg) rotateY(${props.rotateY}deg) rotateZ(${props.rotateZ}deg) translate3d(${props.translateX}px, ${props.translateY}px, ${props.translateZ}px);`);

</script>

<style scoped>
.cube {
    position: absolute;
    transform-style: preserve-3d;
    top: 50%;
    left: 50%;
    width: 100px;
    height: 100px;
}
</style>