<template>
  <div class="Home">
    <!--START HOME HEADER-->
    <div class="Home-header-main">
      <div class="Home-header-inner">
        <img src="../../src/assets/img/Logo.png" alt="" class="logo" />
        <div class="head-icon-main">
          <div class="head-icon-inner">
            <span class="head-icon-div"><Icon icon="ci:chat" class="head-icon" /></span>
            
            24/7 Customer Service
          </div>

          <div class="head-icon-inner">
             <span class="head-icon-div"><Icon icon="dashicons:awards" class="head-icon" /></span>
            
            ISO 9001 Certification Company
          </div>

          <div class="head-icon-inner">
             <span class="head-icon-div"><Icon icon="ri:medal-line" class="head-icon" /></span>
           
            Qualified Expert Professional
          </div>
        </div>
       
      </div>

      <!------------------------MOBILE NAVIGATION-------------------------->
     
        <div class="icon">
          <span :class="{'icon-active' : mobileNav}" v-show="mobile">
            <Icon icon="uim:bars"  @click="toggleMobilNav"  />
          </span>
        </div>
   
        

         <transition name="mobile-nav">
           <div v-show="mobileNav" class="mobile-side">
           <div class="dropdown-nav">
             <span class="logo-nav-main">
              <img src="../../src/assets/img/Logo.png" alt="" class="logo-nav" />
           </span>
          <ul class="side-ul">
        <li class="side-li"><a href="#Home" @click="toggleMobilNav">Home</a></li>
        <li class="side-li"><a href="#About" @click="toggleMobilNav">About</a></li>
        <li class="side-li"><a href="#WhatWeDo" @click="toggleMobilNav">Services</a></li>
        <li class="side-li"><a href="#contact" @click="toggleMobilNav">Contact Us</a></li>
        </ul>
           </div>
           
        </div>
        </transition>
    </div>
    <!--ENDING HOME HEADER-->

    <!--START HOME NAV-->
    <Navigation />
    <!--ENDING HOME NAV-->

    <!--START HOME Slider-->
    <div class="Home-slider-main" id="Home">
      <Slider />
    </div>
    <!--ENDING HOME Slider-->

    <!--START HOME About-->
    <div class="Home-about-main" id="About">
      <About />
    </div>
    <!--ENDING HOME About-->

    <!--START HOME What We Do-->
    <div class="Home-We-Do" id="WhatWeDo">
      <WhatWeDo />
    </div>
    <!--ENDING HOME What We Do-->

    <!--START HOME CASE STUDY-->
    <div class="CaseStudy">
      <CaseStudy />
    </div>
    <!--ENDING HOME CASE STUDY-->

    <!--START HOME FAQ-->
    <div class="FAQ">
      <Faq />
    </div>
    <!--ENDING HOME FAQ-->

    <!--START HOME CUSTOMER FEEDBACK-->
   
    <!--ENDING HOME CUSTOMER FEEDBACK-->
  </div>
</template>

<script>
import { Icon } from "@iconify/vue";
import Navigation from "../components/Nav.vue";
import Slider from "../components/slider.vue";
import About from "../components/about.vue";
import WhatWeDo from "../components/whatWeDo.vue";
import CaseStudy from "../components/caseStudy.vue";
import Faq from "../components/faq.vue";

export default {
  components: {
    Icon,
    Navigation,
    Slider,
    About,
    WhatWeDo,
    CaseStudy,
    Faq,
    
  },
    data(){
    return{
      mobile: null,
      mobileNav:null,
      windowWidth:null,
    }
  },

  created(){
    window.addEventListener('resize', this.checkScreen);
    this.checkScreen();
  },

  methods:{
    toggleMobilNav(){
      this.mobileNav = !this.mobileNav;
    },

  checkScreen(){
    this.windowWidth = window.innerWidth;
    if(this.windowWidth <= 900){
      this.mobile = true;
      return;
    }
    this.mobile = false;
    this.mobileNav = false;
    return;
  }

  }
};
</script>

<style scoped>
.mobile-side{
  z-index: 20;
  width: 100%;
  height: 100%;
  position: fixed;
  background-color: rgba(0, 0, 0, 0.334);
}
.side-li a{
  text-decoration: none;
  color: black;
}
.side-ul{
  height: 300px;
  margin-top: 20px;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
}
.side-li{
  font-size: 20px;
  font-weight: 600;
    padding: 10px;
  display:flex;
  flex-direction: column;
  justify-content: center;
  height: 50px;
  list-style: none;
  border-bottom: 1px solid rgba(0, 0, 0, 0.289);
}
.logo-nav-main{
  margin-top: 30px;
  width: 150px;
}
.logo-nav{
  width: 100%;
}
.icon{
  padding: 5px;
  background-color: rgb(255, 255, 255);
  z-index: 27;
  display: flex;
position: absolute;
  align-items: center;
  top: 1rem;
  right:6rem ;
 height: fit-content;
}
.icon span{
   display: flex;
   justify-content: center;
  align-items: center;
  height: 50px;
  width: 50px;
  cursor: pointer;
  color: black;
  font-size: 40px;
  transition: .8s ease all;
  border-radius: 5px;
  border: 1px solid rgba(0, 0, 0, 0.241);
}
.icon-active{
  transform: rotate(180deg);
}
.dropdown-nav{
  padding: 20px;
  z-index: 50;
  display: flex;
  flex-direction: column;
  position: fixed;
  width: 100%;
  max-width: 250px;
  height: 100%;
  top: 0;
  left: 0;
  background-color: white;
}

@media screen and (max-width: 900px) {
    .icon{
  right:2rem ;
 height: fit-content;
}
}
</style>
