

<template>
  <div class="home">
    <a-assets>
  <!-- These will not block. -->
  <audio id="theme" preload="auto" on="click" v-bind:src="'@/assets/theme_music_1.mp3'" autoplay="true" volume="-1"></audio>
  <audio id="ding" preload="auto" v-bind:src="'@/assets/ding_1.mp3'" on="click"></audio>

  <audio id="dub" preload="auto" v-bind:src="'@/assets/incorrect_2.mp3'" on="click"></audio>
</a-assets>
<a-scene sound="src: #theme" volume="-1" loop="true" autoplay="true" v-bind:src="'@/assets/theme_music_1.mp3'" positional= "true">
  <a-entity id="camera" camera="userHeight: 1.6" look-controls cursor="rayOrigin: mouse"></a-entity>



  <a-entity cursor position="0 0 -5"></a-entity>
  <a-entity
    position="0 3 -3"
    geometry="primitive: plane; width: 4; height: auto"
    material="color: black"
    text="value: .....toca la caja"
    sound="src: #dub;
    on=click"
   
  ></a-entity>

  <a-box
    position="-1 0.5 -3"
    rotation="0 45 0"
    color="#4CC3D9"
    sound="src: #ding;
    on: click"
    shadow
    event-set__enter="_event: mouseenter; color: #026fc9"
    event-set__leave="_event: mouseleave; color: #4CC3D9"
  >
    <a-entity text="value: la caja;"></a-entity>
    <!-- This animation begins when the box is clicked with the mouse. -->
    <a-animation
      attribute="rotation"
      dur="3000"
      fill="forwards"
      to="0 360 0"
      direction="alternate"
      begin="click"
    ></a-animation>
  </a-box>

  <a-sphere
  event-set__enter="_event: mouseenter; color: #026fc9"
  event-set__leave="_event: mouseleave; color: #EF2D5E"
    position="0 1.25 -5"
    radius="1.25"
    color="#EF2D5E"
    sound="src: #dub;
    on: click"
    shadow
   
  >
    <!-- This animation begins when the sphere is clicked with the mouse. -->
    <!-- <a-animation
      attribute="position"
      dur="1000"
      fill="forwards"
      to="0 2.5 -6"
      direction="alternate"
      begin="click"
    ></a-animation> -->
  </a-sphere>
  <a-entity text="value: la esfera;" width="1000" height="1000" color="black" position="0 1.25 -5"></a-entity>

  <a-triangle
  event-set__enter="_event: mouseenter; color: #026fc9"
  event-set__leave="_event: mouseleave; color: #EF2D5E"
    position="1 0.75 -3"
    radius="1.25"
    color="#EF2D5E"
    sound="src: #dub;
    on: click"
    shadow

  >
    <!-- This animation begins when the triangle is clicked with the mouse. -->
    <!-- <a-animation
      attribute="rotation"
      dur="1000"
      fill="forwards"
      to="0 2.5 -6"
      direction="alternate"
      begin="click"
    ></a-animation> -->
  </a-triangle>
  <a-entity
    geometry="primitive: plane; width: 4; height: auto"
    material="color: blue"
    text="value: This text will be 4 units wide."
  ></a-entity>

  <a-plane position="0 0 -4" rotation="-90 0 0" width="4" height="4" color="#7BC8A4" shadow></a-plane>
  <!-- Out of the box environment! -->
  <a-entity
    environment="preset: tron
; numDressing: 500"
  ></a-entity>
</a-scene>

  </div>
</template>

<style>
</style>

<script>
export default {
  data: function() {
    return {
      message: "Welcome to Vue.js!"
    };
  },
  created: function() {},
  methods: {}
};
</script>
