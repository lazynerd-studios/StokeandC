<template>
  <div class="Nav-main">
    <nav class="Nav-inner" v-show="!mobile">
      <ul>
        <li><a href="#Home">Home</a></li>
        <li><a href="#About">About</a></li>
        <li><a href="#WhatWeDo">Services</a></li>
        <li><a href="#contact">Contact Us</a></li>
      </ul>
      <a href="#contact" class="nav-btn">
        <button>
        Get A Quote <Icon icon="ant-design:plus-outlined" class="button-icon" />
      </button>
      </a>
      
    </nav>
   

   
  </div>
</template>

<script>
import { Icon } from "@iconify/vue";

export default {
  components: {
    Icon,
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


