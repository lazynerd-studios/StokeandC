<template>
  <div
    id="app"
    class="wrapper"
    v-cloak
    v-bind:class="{ 'is-previous': isPreviousSlide, 'first-load': isFirstLoad }"
  >
    <div
      class="slide-wrapper"
      v-for="(slide, index) in slides"
      :key="index"
      v-bind:class="{ active: index === currentSlide }"
      v-bind:style="{
        'z-index': slides.length - index,
        'background-image': 'url(' + slide.bgImg + ')',
      }"
      v-on:mouseover="stopRotation"
      v-on:mouseout="startRotation"
    >
      <div class="slide-inner">
        <div class="slide-bg-text">
          <p>{{ slide.headlineFirstLine }}</p>
          <p>{{ slide.headlineSecondLine }}</p>
        </div>
        <div class="slide-rect-filter"></div>
        <div class="slide-content">
          <h1 class="slide-content-text">
            <p class="slide-content-text1">{{ slide.headlineFirstLine }}</p>
            <p class="slide-content-text2">{{ slide.headlineSecondLine }}</p>
          </h1>
        
        </div>
        
      </div> 
                        
                       
    </div>
    <div class="controls-container"></div>
    <div class="pagination-container">
      <span
        class="pagination-item"
        v-for="(slide, index) in slides"
        :key="index"
        v-bind:class="{ active: index === currentSlide }"
        v-on:click="updateSlide(index)"
        v-on:mouseover="stopRotation"
        v-on:mouseout="startRotation"
      ></span>
    </div>
  </div>
</template>

<script>
import rigImg1 from "../assets/img/rigImg1.jpg"
import rigImg2 from "../assets/img/rigImg2.jpg"
import rigImg3 from "../assets/img/rigimg3.jpg"
export default {
  name: "slider",
  data: () => ({
    currentSlide: 0,
    isPreviousSlide: false,
    isFirstLoad: true,
    slides: [
      {
        headlineFirstLine: "Welcome to Stoke and Caldwell,",
        headlineSecondLine: "An oil-rig servicing company",
        sublineFirstLine: "",
        sublineSecondLine: "",
        bgImg: rigImg1 ,
        // rectImg: "https://i.postimg.cc/vTW0XkvM/slide-rect0.jpg",
      },
      {
        headlineFirstLine: "We are Stoke and Caldwell",
        headlineSecondLine: "We render engineering procurement and construction",
        sublineFirstLine: "Il n'y a rien de neuf sous",
        sublineSecondLine: "le soleil",
        bgImg: rigImg2 ,
        rectImg: "https://i.postimg.cc/ryWZ8R2b/slide-rect1.jpg",
      },
      {
        headlineFirstLine: "We are Stoke and Caldwell",
        headlineSecondLine: "We also offer marine services and manpower supply to the oil and gas industry ",
        sublineFirstLine: "Τίποτα καινούργιο κάτω από",
        sublineSecondLine: "τον ήλιο",
        bgImg: rigImg3 ,
        rectImg: "https://i.postimg.cc/3JFLGMRF/slide-rect2.jpg",
      },
    ],
  }),
  mounted: function () {
    var productRotatorSlide = document.getElementById("app");
    var startX = 0;
    var endX = 0;

    productRotatorSlide.addEventListener(
      "touchstart",
      (event) => (startX = event.touches[0].pageX)
    );

    productRotatorSlide.addEventListener(
      "touchmove",
      (event) => (endX = event.touches[0].pageX)
    );

    productRotatorSlide.addEventListener(
      "touchend",
      function () {
        var threshold = startX - endX;

        if (threshold < 150 && 0 < this.currentSlide) {
          this.currentSlide--;
        }
        if (threshold > -150 && this.currentSlide < this.slides.length - 1) {
          this.currentSlide++;
        }
      }.bind(this.event)
    );
    this.startRotation();
  },
  methods: {
    updateSlide(index) {
      index < this.currentSlide
        ? (this.isPreviousSlide = true)
        : (this.isPreviousSlide = false);
      this.currentSlide = index;
      this.isFirstLoad = false;
    },
    startRotation() {
      this.timer = setInterval(this.next, 5000);
    },
    next() {
      this.currentSlide < this.slides.length - 1
        ? this.updateSlide(this.currentSlide + 1)
        : this.updateSlide(0);
    },
    stopRotation() {
      clearTimeout(this.timer);
      this.timer = null;
    },
  },
};
</script>

<style scoped>

.button-icon-slide{
    border-radius: 5px;
    background-color: rgba(11, 255, 202, 0.7);
    padding: 7px;
    font-size: 35px;
    transition: 0.5s;
   
}

.slide-side-text,
.slide-content-cta {
  font-family: "Montserrat";
  text-transform: uppercase;
  color: #fff;
  letter-spacing: 0.12rem;
  font-size: 0.7rem;
  line-height: 1;
}



[v-cloak] {
  opacity: 0;
}

body {
  cursor: default;
}
body ::-moz-selection {
  background-color: rgba(46, 49, 52, 0.7);
  color: #f5f5f1;
}
body ::selection {
  background-color: rgba(46, 49, 52, 0.7);
  color: #f5f5f1;
}
body ::-moz-selection {
  background-color: rgba(46, 49, 52, 0.7);
  color: #f5f5f1;
}

.wrapper {
  height: 100vh;
  min-height: 36rem;
  position: relative;
}
@media (max-width: 630px) {
  .wrapper {
    height: 90vh;
    min-height: 0;
  }
}

.slide-wrapper {
  background-size: cover;
  height: 100%;
  background-position: center center;
  position: absolute;
  width: 100%;
  background-blend-mode: darken;
}
.slide-wrapper:nth-child(1) {
  background-color: rgba(115, 129, 153, 0.4);
}
.slide-wrapper:nth-child(1):before {
  background-color: rgba(14, 18, 23, 0.729);
}
.slide-wrapper:nth-child(1) .slide-content-text {
  text-shadow: 2px 5px 45px rgba(85, 96, 113, 0.25);
}
.slide-wrapper:nth-child(2) {
  background-color: rgba(144, 171, 184, 0.7);
}
.slide-wrapper:nth-child(2):before {
  background-color: rgba(14, 18, 23, 0.729);
}
.slide-wrapper:nth-child(2) .slide-content-text {
  text-shadow: 2px 5px 45px rgba(121, 142, 152, 0.2);
}
.slide-wrapper:nth-child(3) {
  background-color: rgba(86, 125, 156, 0.5);
}
.slide-wrapper:nth-child(3):before {
  background-color: rgba(14, 18, 23, 0.729);
}
.slide-wrapper:nth-child(3) .slide-content-text {
  text-shadow: 2px 5px 55px rgba(57, 83, 103, 0.4);
}
.slide-wrapper:before {
  content: "";
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 1;
}
.slide-inner {
  position: relative;
  z-index: 2;
  height: 100%;
  overflow: hidden;
}
.slide-bg-text {
  font-family: "Playfair Display";
  color: #000;
  font-size: 42vh;
  line-height: 0.8;
  opacity: 0.03;
  font-weight: 900;
  margin-top: -4rem;
  position: absolute;
  top: 50%;
  left: 5vw;
  transform: translateY(-50%);
}
.slide-bg-text > p:last-child {
  padding-left: 4rem;
}
.slide-content {
  color: #fff;
  margin-top: 3rem;
  position: absolute;
  top: 50%;
  left: calc(-2vw + (0.7) * 48vh);
  transform: translateY(-50%);
  display: flex;
  flex-direction: column;
}
@media (max-width: 1000px) {
  .slide-content {
    left: calc(-2vw + (0.7) * 16vw);
  }
}
@media (max-width: 730px) {
  .slide-content {
    top: 30%;
    transform: translateY(-30%);
    left: calc(-2vw + (0.7) * 16vw);
  }
}
.slide-content-text1{
     font-size: 2rem;
     margin-bottom: 10px;
}
.slide-content-text2{
     font-size: 5rem;
}
.slide-content-text {
  font-family: "Playfair Display";
  width: 1000px;
  letter-spacing: 0.1rem;
  line-height: 0.87;
  font-weight: 600;
  will-change: auto;
}

@media (max-width: 1150px) {
  .slide-content-text2 {
    font-size: 3rem;
  }
  .slide-content-text {
  font-family: "Playfair Display";
  width: 700px;
  letter-spacing: 0.1rem;
  line-height: 0.87;
  font-weight: 600;
  will-change: auto;
}
}
@media (max-width: 840px) {
  .slide-content-text2 {
    font-size: 2.5rem;
  }
}
@media (max-width: 750px) {
  .slide-content-text2{
     font-size: 3rem;
}
.slide-content-text {
  font-family: "Playfair Display";
  width: 600px;
  letter-spacing: 0.1rem;
  
}
}
@media (max-width: 630px) {
  .slide-content-text2 {
    margin-bottom: 2.5rem;
  }
}
@media (max-width: 560px) {
  .slide-content-text1 {
    font-size: 1.5rem;
  }
  .slide-content-text2 {
    font-size: 2rem;
  }
  .slide-content-text {
  font-family: "Playfair Display";
  width: 400px;
  letter-spacing: 0.1rem;
  
}
}
.slide-content-text > p:last-child {
  padding-left: 3rem;
}
.slide-content-cta {
  cursor: pointer;
  align-self: flex-start;
  display: inline-flex;
  justify-content: space-around;
  align-items: center;
  margin-top: 4.5rem;
  margin-left: calc((0.3) * 4vh + 2.5rem);
 height: 50px;
 width: 180px;
 background-color: #00d09b;
 border-radius: 5px;
  transition: 0.18s ease-in-out;
  font-weight: 700;
  font-size: 17px;
}
@media (max-width: 1000px) {
  .slide-content-cta {
    background-color: rgba(255, 255, 255, 0.3);
    padding-top: 1.2rem;
    padding-bottom: 1.2rem;
  }
}
@media (max-width: 630px) {
  .slide-content-cta {
    display: none;
  }
}
.slide-content-cta:hover {
  color:white;
  background-color: rgb(9, 54, 161);
}
.slide-rect {
  height: 62vh;
  width: 48vh;
  border-image-slice: 10%;
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  left: 13vw;
  border-width: 5vh;
  border-style: solid;
  box-shadow: 2px 2px 90px 30px rgba(41, 50, 61, 0.22);
  will-change: auto;
}
@media (max-height: 790px) {
  .slide-rect {
    left: 9vw;
    height: 20vw;
    width: 16vw;
    border-width: 5vh;
  }
}
@media (max-height: 730px) {
  .slide-rect {
    top: 30%;
    transform: translateY(-30%);
  }
}
.slide-rect-filter {
  filter: brightness(110%) contrast(110%) saturate(110%);
}
.slide-sec1-icon{
  transform: rotate(90deg);
  font-size: 25px;
  margin-top: 7px;
}
.slide-side-text {
  display: flex;
  font-size: 15px;
  justify-content: space-between;
  height: 450px;
 margin-top: -120px;
  position: absolute;
  left: calc(13vw - 3rem);
  -ms-writing-mode: tb-rl;
  writing-mode: vertical-rl;
  top: calc((50% - (62vh / 2)) + (5vh / 2));
}
@media (max-height: 790px) {
  .slide-side-text {
    left: calc(9vw - 3rem);
    top: calc((50% - (20vw / 2)) + (5vh / 2));
  }
}
@media (max-height: 730px) {
  .slide-side-text {
    top: calc((40% - (20vw / 2)) + (5vh / 2));
  }
}
.slide-side-text > span:first-child {
  font-weight: 700;
}


.controls-container {
  position: absolute;
  z-index: 200;
  display: flex;
  bottom: 0;
  right: 0;
  align-items: flex-end;
}
@media (max-width: 630px) {
  .controls-container {
    display: none;
  }
}
.controls-button {
  cursor: pointer;
  background-color: rgba(208, 206, 204, 0.32);
  border: 0;
  padding: 1.6rem 2.2rem;
  flex-basis: 0;
  flex-grow: 1;
  min-width: 15rem;
  transition: 0.25s ease-in-out;
  outline: 0;
}
@media (max-width: 730px) {
  .controls-button {
    padding: 1.2rem 1.4rem;
    min-width: 13rem;
  }
}
.controls-button:not(.active):hover {
  color: #000;
  background-color: #fff;
}
.controls-button.active {
  cursor: default;
  font-weight: 700;
  background-color: #3b3e45;
  padding-top: 1.9rem;
  padding-bottom: 1.9rem;
  margin-bottom: -0.3rem;
  position: relative;
}
@media (max-width: 730px) {
  .controls-button.active {
    padding-top: 1.4rem;
    padding-bottom: 1.4rem;
    margin-bottom: -0.15rem;
  }
}
.controls-button.active:after {
  content: "";
  background-color: #e3e3e3;
  height: 5px;
  width: calc(100% - 8px);
  position: absolute;
  top: 100%;
  left: 4px;
}
.controls-button:not(.active) + .controls-button {
  border-left: 1px solid rgba(255, 255, 255, 0.2);
}

.pagination-container {
  position: absolute;
  z-index: 200;
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  right: 2rem;
  top: 50%;
  transform: translateY(-50%);
}
@media (max-width: 920px) {
  .pagination-container {
    display: none;
  }
}
.pagination-item {
  width: 30px;
  height: 30px;
  border-radius: 50%;
  background-color: rgba(255, 255, 255, 0.6);
  transition: 0.18s ease-in-out;
}
.pagination-item + .pagination-item {
  margin-top: 1rem;
}
.pagination-item.active {
  background-color: #fff;
  position: relative;
  transform: translateX(-0.6rem);
  width: 35px;
  height: 35px;
}
.pagination-item.active:after {
  content: "";
  height: 4px;
  width: 2px;
  border-radius: 35%;
  background-color: #fff;
  display: inline-block;
  position: absolute;
  right: 0;
  top: 50%;
  transform: translateX(0.6rem) translateY(-50%);
}
.pagination-item:not(.active) {
  cursor: pointer;
}
.pagination-item:not(.active):hover {
  background-color: #fff;
  width: 35px;
}

@-webkit-keyframes slideLeft {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(-100%);
  }
}

@keyframes slideLeft {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(-100%);
  }
}
@-webkit-keyframes slideRight {
  from {
    transform: translateX(-100%);
  }
  to {
    transform: translateX(0);
  }
}
@keyframes slideRight {
  from {
    transform: translateX(-100%);
  }
  to {
    transform: translateX(0);
  }
}
@-webkit-keyframes cutTextUp {
  from {
    -webkit-clip-path: inset(0 0 -10% 0);
    clip-path: inset(0 0 -10% 0);
  }
  to {
    -webkit-clip-path: inset(0 0 100% 0);
    clip-path: inset(0 0 100% 0);
  }
}
@keyframes cutTextUp {
  from {
    -webkit-clip-path: inset(0 0 -10% 0);
    clip-path: inset(0 0 -10% 0);
  }
  to {
    -webkit-clip-path: inset(0 0 100% 0);
    clip-path: inset(0 0 100% 0);
  }
}
@-webkit-keyframes cutTextDown {
  from {
    -webkit-clip-path: inset(100% 0 0 0);
    clip-path: inset(100% 0 0 0);
  }
  to {
    -webkit-clip-path: inset(-10% 0 -20% 0);
    clip-path: inset(-10% 0 -20% 0);
    opacity: 1;
  }
}
@keyframes cutTextDown {
  from {
    -webkit-clip-path: inset(100% 0 0 0);
    clip-path: inset(100% 0 0 0);
  }
  to {
    -webkit-clip-path: inset(-10% 0 -20% 0);
    clip-path: inset(-10% 0 -20% 0);
    opacity: 1;
  }
}
@-webkit-keyframes cutTextDownFromTop {
  from {
    -webkit-clip-path: inset(0 0 100% 0);
    clip-path: inset(0 0 100% 0);
  }
  to {
    -webkit-clip-path: inset(0 0 -30% 0);
    clip-path: inset(0 0 -30% 0);
    opacity: 1;
  }
}
@keyframes cutTextDownFromTop {
  from {
    -webkit-clip-path: inset(0 0 100% 0);
    clip-path: inset(0 0 100% 0);
  }
  to {
    -webkit-clip-path: inset(0 0 -30% 0);
    clip-path: inset(0 0 -30% 0);
    opacity: 1;
  }
}
@-webkit-keyframes rectMovement {
  0% {
    transform: translateX(0) rotate(0) translateY(-50%);
  }
  60% {
    opacity: 1;
  }
  100% {
    transform: translateX(calc(-48vh + -13vw)) rotate(12deg) translateY(-50%);
    opacity: 0;
  }
}
@keyframes rectMovement {
  0% {
    transform: translateX(0) rotate(0) translateY(-50%);
  }
  60% {
    opacity: 1;
  }
  100% {
    transform: translateX(calc(-48vh + -13vw)) rotate(12deg) translateY(-50%);
    opacity: 0;
  }
}
@media (max-height: 730px) {
  @-webkit-keyframes rectMovement {
    0% {
      transform: translateX(0) rotate(0) translateY(-30%);
    }
    60% {
      opacity: 1;
    }
    100% {
      transform: translateX(calc(-48vh + -13vw)) rotate(12deg) translateY(-30%);
      opacity: 0;
    }
  }
  @keyframes rectMovement {
    0% {
      transform: translateX(0) rotate(0) translateY(-30%);
    }
    60% {
      opacity: 1;
    }
    100% {
      transform: translateX(calc(-48vh + -13vw)) rotate(12deg) translateY(-30%);
      opacity: 0;
    }
  }
}
@-webkit-keyframes rectMovementFromRight {
  0% {
    transform: translateX(calc(48vh)) rotate(12deg) translateY(-50%);
    opacity: 0;
  }
  60% {
    opacity: 1;
  }
  100% {
    transform: translateX(0) rotate(0) translateY(-50%);
    opacity: 1;
    @media (max-height: 730px) {
      transform: translateX(0) rotate(0) translateY(-30%);
    }
  }
}
@keyframes rectMovementFromRight {
  0% {
    transform: translateX(calc(48vh)) rotate(12deg) translateY(-50%);
    opacity: 0;
  }
  60% {
    opacity: 1;
  }
  100% {
    transform: translateX(0) rotate(0) translateY(-50%);
    opacity: 1;
    @media (max-height: 730px) {
      transform: translateX(0) rotate(0) translateY(-30%);
    }
  }
}
@media (max-height: 730px) {
  @-webkit-keyframes rectMovementFromRight {
    0% {
      transform: translateX(calc(48vh)) rotate(12deg) translateY(-30%);
      opacity: 0;
    }
    60% {
      opacity: 1;
    }
    100% {
      transform: translateX(0) rotate(0) translateY(-30%);
      opacity: 1;
    }
  }
  @keyframes rectMovementFromRight {
    0% {
      transform: translateX(calc(48vh)) rotate(12deg) translateY(-30%);
      opacity: 0;
    }
    60% {
      opacity: 1;
    }
    100% {
      transform: translateX(0) rotate(0) translateY(-30%);
      opacity: 1;
    }
  }
}
@-webkit-keyframes rectMovementRight {
  0% {
    transform: translateX(calc(-48vh + -13vw)) rotate(12deg) translateY(-50%);
  }
  40% {
    opacity: 1;
  }
  100% {
    transform: translateX(0) rotate(0) translateY(-50%);
    opacity: 1;
    @media (max-height: 730px) {
      transform: translateX(0) rotate(0) translateY(-30%);
    }
  }
}
@keyframes rectMovementRight {
  0% {
    transform: translateX(calc(-48vh + -13vw)) rotate(12deg) translateY(-50%);
  }
  40% {
    opacity: 1;
  }
  100% {
    transform: translateX(0) rotate(0) translateY(-50%);
    opacity: 1;
    @media (max-height: 730px) {
      transform: translateX(0) rotate(0) translateY(-30%);
    }
  }
}
@media (max-height: 730px) {
  @-webkit-keyframes rectMovementRight {
    0% {
      transform: translateX(calc(-48vh + -13vw)) rotate(12deg) translateY(-30%);
    }
    40% {
      opacity: 1;
    }
    100% {
      transform: translateX(0) rotate(0) translateY(-30%);
      opacity: 1;
    }
  }
  @keyframes rectMovementRight {
    0% {
      transform: translateX(calc(-48vh + -13vw)) rotate(12deg) translateY(-30%);
    }
    40% {
      opacity: 1;
    }
    100% {
      transform: translateX(0) rotate(0) translateY(-30%);
      opacity: 1;
    }
  }
}
@-webkit-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
.slide-wrapper {
  opacity: 0;
  transition-delay: 1.4s;
  transition-duration: 0s;
  transition-property: opacity;
  will-change: opacity, transform;
}
.slide-wrapper:not(.active) {
  -webkit-animation-delay: 0.5s;
  animation-delay: 0.5s;
  -webkit-animation-name: slideLeft;
  animation-name: slideLeft;
  -webkit-animation-duration: 0.9s;
  animation-duration: 0.9s;
  -webkit-animation-timing-function: cubic-bezier(0.18, 0.54, 0.52, 0.93);
  animation-timing-function: cubic-bezier(0.18, 0.54, 0.52, 0.93);
  pointer-events: none;
}
.slide-wrapper:not(.active) .slide-content-text > p,
.slide-wrapper:not(.active) .slide-side-text {
  -webkit-animation-name: cutTextUp;
  animation-name: cutTextUp;
  -webkit-animation-duration: 0.5s;
  animation-duration: 0.5s;
  -webkit-animation-timing-function: ease-out;
  animation-timing-function: ease-out;
}
.slide-wrapper:not(.active) .slide-rect {
  -webkit-animation-name: rectMovement;
  animation-name: rectMovement;
  -webkit-animation-duration: 0.5s;
  animation-duration: 0.5s;
  -webkit-animation-timing-function: ease;
  animation-timing-function: ease;
  -webkit-animation-fill-mode: forwards;
  animation-fill-mode: forwards;
}
.slide-wrapper.active {
  transition-delay: 0s;
  opacity: 1;
}
.slide-wrapper.active .slide-content-text > p {
  opacity: 0;
  -webkit-animation-delay: 0.8s;
  animation-delay: 0.8s;
  -webkit-animation-name: cutTextDown;
  animation-name: cutTextDown;
  -webkit-animation-duration: 0.5s;
  animation-duration: 0.5s;
  -webkit-animation-timing-function: ease;
  animation-timing-function: ease;
  -webkit-animation-fill-mode: forwards;
  animation-fill-mode: forwards;
}
.slide-wrapper.active .slide-rect {
  opacity: 0;
  -webkit-animation-name: rectMovementFromRight;
  animation-name: rectMovementFromRight;
  -webkit-animation-duration: 0.45s;
  animation-duration: 0.45s;
  -webkit-animation-timing-function: ease;
  animation-timing-function: ease;
  -webkit-animation-fill-mode: forwards;
  animation-fill-mode: forwards;
  -webkit-animation-delay: 0.9s;
  animation-delay: 0.9s;
}
.is-previous .slide-wrapper:not(.active) {
  -webkit-animation: none;
  animation: none;
}
.is-previous .slide-wrapper:not(.active) .slide-rect {
  -webkit-animation: none;
  animation: none;
}
.is-previous .slide-wrapper.active {
  transform: translateX(-100%);
  -webkit-animation-fill-mode: forwards;
  animation-fill-mode: forwards;
  -webkit-animation-delay: 0.5s;
  animation-delay: 0.5s;
  -webkit-animation-name: slideRight;
  animation-name: slideRight;
  -webkit-animation-duration: 0.8s;
  animation-duration: 0.8s;
  -webkit-animation-timing-function: cubic-bezier(0.18, 0.54, 0.52, 0.93);
  animation-timing-function: cubic-bezier(0.18, 0.54, 0.52, 0.93);
}
.is-previous .slide-wrapper.active .slide-rect {
  opacity: 0;
  -webkit-animation-name: rectMovementRight;
  animation-name: rectMovementRight;
  -webkit-animation-duration: 0.5s;
  animation-duration: 0.5s;
  -webkit-animation-timing-function: ease-out;
  animation-timing-function: ease-out;
  -webkit-animation-fill-mode: forwards;
  animation-fill-mode: forwards;
  -webkit-animation-delay: 0.9s;
  animation-delay: 0.9s;
}

.first-load .slide-wrapper.active .slide-side-text,
.first-load .slide-wrapper.active .slide-content-cta,
.first-load .slide-wrapper.active .slide-rect,
.first-load .controls-container {
  opacity: 0;
  -webkit-animation-name: fadeIn;
  animation-name: fadeIn;
  -webkit-animation-delay: 0.3s;
  animation-delay: 0.3s;
  -webkit-animation-duration: 0.3s;
  animation-duration: 0.3s;
  -webkit-animation-fill-mode: forwards;
  animation-fill-mode: forwards;
  -webkit-animation-timing-function: ease-in;
  animation-timing-function: ease-in;
}
.first-load .slide-wrapper.active .slide-content-text > p {
  -webkit-animation-name: fadeIn;
  animation-name: fadeIn;
  -webkit-animation-delay: 0.5s;
  animation-delay: 0.5s;
  -webkit-animation-duration: 0.7s;
  animation-duration: 0.7s;
}

@media (max-width: 400px){
.slide-content-text[data-v-91c82b1e] {
    font-size: 1.5rem;
    width: 340px;
    line-height: 50px;
}
  
.slide-side-text {
  margin-left: 20px;
}
  .slide-content {
    top: 30%;
    transform: translateY(-30%);
    left: calc(3vw + (0.7) * 16vw);
  }
  .slide-content-text > p:last-child {
  padding-left: 1rem;
}

}
</style>

