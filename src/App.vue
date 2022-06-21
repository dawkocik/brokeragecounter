<template>
  <div class="background">
    <span></span>
    <span></span>
    <span></span>
    <span></span>
    <span></span>
    <span></span>
    <span></span>
    <span></span>
    <span></span>
    <span></span>
    <span></span>
    <span></span>
    <span></span>
    <span></span>
  </div>
  <div class="container">
    <shift-timer></shift-timer>
    <div class="counter-container">
      <package-counter name="RFC"></package-counter>
      <package-counter name="EOR"></package-counter>
    </div>
  </div>
</template>

<script>
import PackageCounter from "@/components/package-counter";
import ShiftTimer from "@/components/shift-timer";

export default {
  name: 'App',
  components: {
    ShiftTimer,
    PackageCounter,
  }
}

</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Lato&display=swap');

html {
  /*background-image: linear-gradient(to right top, #051937, #143164, #2b4a95, #4864c8, #6a7efd);*/
  height: 100vh;
  margin: 0;
  background-attachment: fixed;
  font-family: 'Lato', sans-serif;
}

.container {
  background-color: #00000022;
  border-radius: 35px;
  width: 600px;
  backdrop-filter: blur(50px);

  position: absolute;
  left: 50%;
  top: 50%;
  -webkit-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
}

.counter-container {
  margin-top: 20px;
}

@keyframes move {
  100% {
    transform: translate3d(0, 0, 1px) rotate(360deg);
  }
}

.background {
  position: fixed;
  width: 100vw;
  height: 100vh;
  top: 0;
  left: 0;
  background: #301506;
  overflow: hidden;
}

.background span {
  width: 30vmin;
  height: 30vmin;
  border-radius: 30vmin;
  backface-visibility: hidden;
  position: absolute;
  animation: move;
  animation-duration: 8;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
}


.background span:nth-child(0) {
  color: #fab80a;
  top: 13%;
  left: 86%;
  animation-duration: 101s;
  animation-delay: -276s;
  transform-origin: 2vw 12vh;
  box-shadow: -60vmin 0 8.273966672117275vmin currentColor;
}

.background span:nth-child(1) {
  color: #fab80a;
  top: 58%;
  left: 41%;
  animation-duration: 96s;
  animation-delay: -273s;
  transform-origin: -21vw 13vh;
  box-shadow: 60vmin 0 7.578372353721872vmin currentColor;
}

.background span:nth-child(2) {
  color: #fab80a;
  top: 79%;
  left: 37%;
  animation-duration: 254s;
  animation-delay: -388s;
  transform-origin: 14vw -23vh;
  box-shadow: -60vmin 0 7.551142754084502vmin currentColor;
}

.background span:nth-child(3) {
  color: #fab80a;
  top: 97%;
  left: 73%;
  animation-duration: 123s;
  animation-delay: -25s;
  transform-origin: 12vw -12vh;
  box-shadow: 60vmin 0 8.06961171141373vmin currentColor;
}

.background span:nth-child(4) {
  color: #fab80a;
  top: 16%;
  left: 66%;
  animation-duration: 380s;
  animation-delay: -242s;
  transform-origin: -4vw 21vh;
  box-shadow: 60vmin 0 8.212860072141067vmin currentColor;
}

.background span:nth-child(5) {
  color: #fab80a;
  top: 40%;
  left: 31%;
  animation-duration: 347s;
  animation-delay: -303s;
  transform-origin: 21vw 7vh;
  box-shadow: 60vmin 0 7.6902555953164065vmin currentColor;
}

.background span:nth-child(6) {
  color: #fab80a;
  top: 78%;
  left: 39%;
  animation-duration: 313s;
  animation-delay: -314s;
  transform-origin: 25vw 10vh;
  box-shadow: 60vmin 0 8.447413023881792vmin currentColor;
}

.background span:nth-child(7) {
  color: #fab80a;
  top: 85%;
  left: 75%;
  animation-duration: 375s;
  animation-delay: -416s;
  transform-origin: -23vw -4vh;
  box-shadow: 60vmin 0 8.157636091696418vmin currentColor;
}

.background span:nth-child(8) {
  color: #fab80a;
  top: 24%;
  left: 81%;
  animation-duration: 307s;
  animation-delay: -37s;
  transform-origin: -12vw -1vh;
  box-shadow: -60vmin 0 7.642825223949975vmin currentColor;
}

.background span:nth-child(9) {
  color: #fab80a;
  top: 62%;
  left: 55%;
  animation-duration: 154s;
  animation-delay: -408s;
  transform-origin: 15vw 6vh;
  box-shadow: -60vmin 0 7.738282097157875vmin currentColor;
}

.background span:nth-child(10) {
  color: #fab80a;
  top: 58%;
  left: 74%;
  animation-duration: 183s;
  animation-delay: -164s;
  transform-origin: 15vw -13vh;
  box-shadow: -60vmin 0 8.095401325261522vmin currentColor;
}

.background span:nth-child(11) {
  color: #fab80a;
  top: 40%;
  left: 51%;
  animation-duration: 27s;
  animation-delay: -140s;
  transform-origin: -7vw -7vh;
  box-shadow: 60vmin 0 7.553115944548761vmin currentColor;
}

.background span:nth-child(12) {
  color: #fab80a;
  top: 99%;
  left: 76%;
  animation-duration: 141s;
  animation-delay: -225s;
  transform-origin: 19vw 21vh;
  box-shadow: -60vmin 0 7.569755914492453vmin currentColor;
}

.background span:nth-child(13) {
  color: #fab80a;
  top: 38%;
  left: 67%;
  animation-duration: 323s;
  animation-delay: -405s;
  transform-origin: 11vw -24vh;
  box-shadow: 60vmin 0 8.472473033951406vmin currentColor;
}

</style>
