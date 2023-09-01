<template>
  <div>
    <!-- THE TRANSPORT DEFINITELY STARTS TICKING UP -->
    <button @click="startTransport">Start</button>
    <button @click="stopTransport">Stop</button>
    <button @click="updateTransportInfo">Click to see change did occur</button>
    <div>Position Direct: {{ Tone.Transport.position }}</div>
    <div>Position Ref: {{ transportPosition }}</div>
  </div>
</template>

<script setup>

import { ref } from 'vue';
import * as Tone from 'tone';

// MAKE REF TO POSITION PROPERTY
const transportPosition = ref(Tone.Transport.position);

// START TONE AND TRANSPORT ROLLING
function startTransport() {
  Tone.start();
  Tone.Transport.start();
}

// STOP TRANSPORT
function stopTransport() {
  Tone.Transport.stop();
}

// DEBUGGING STUFF, CLICK TO SEE THAT POSITION IS CHANGING
function updateTransportInfo() {
  transportPosition.value = Tone.Transport.position;
}


</script>

<style scoped></style>
