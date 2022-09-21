<template>
    <div class="About-main">
   <div class="container-1">
       
       <div class="container-1-img1"><img src="../assets/img/image1.jpg" alt="" ></div>
       <div class="container-1-div"><h1 class="twenty">20+</h1><h2>years</h2></div>
       <div class="container-1-img2"><img src="../assets/img/image2.jpg" alt="" ></div>
   </div>

   <div class="container-2">
       <div class="container-2-div1">About Industo</div>

       <div class="container-2-div2">
           <h2 class="container-2-h2">Providing Full Range of High Services Solution Worldwide</h2>
       <p class="container-2-p">Industo is an active company based on valve sector since 1981,
            that follows global developments carefully, pioneer and innovator.</p>
       </div>

       <div class="container-2-div3-main">
           <div class="container-2-div3 div3-inner">
               <span class="about-icon" ><Icon icon="fluent:globe-location-20-regular" class="about-icon-inner"  /></span>
               
               <h3>Worldwide Manufacturing</h3>
               <p>We are the leaders in the building industries, factories.</p>
               </div>

           <div class="container-2-div4 div3-inner">
                <span class="about-icon"><Icon icon="dashicons:awards" class="about-icon-inner"  /></span>
               
                  <h3>Best Quality Service</h3>
               <p> We're wordl wide. We never give up on the challenges.</p>
               </div>

           </div>
           <a href="http://" target="_blank" rel="noopener noreferrer" class="about-link">
           <button class="About-btn">explore more<Icon icon="ant-design:plus-outlined" class="abt-button-icon" /></button>
           </a>
   </div>

   
    </div>
    
</template>

<script>
import { Icon } from '@iconify/vue';

export default {
	components: {
		Icon,
	},

};

</script>