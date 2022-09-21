<template>
    <div>
        <div class="case-study-inner1">
            
            <h2>Featured Projects</h2>
        </div>

        <div class="case-study-slider-main">
            <div class="case-study-slide1">
                  

                    <p>
                       We ensure that all projects handled by us are delivered on time, thanks to our dedicated and highly skilled staff
                    </p>

                      
            </div>


            <div class="case-study-slide2">
                <div class="case-study-slide2-inner">
                    <vueper-slides fade :touchable="false" :arrows="false" fixed-height="500px">
                    <vueper-slide
                        v-for="(slide, i) in slides"
                        
                        :key="i"
                        :image="slide.image"
                        class="case-img"
                        />
                        
                    </vueper-slides>
                </div>

            </div>
        </div>
    </div>
</template>

<script>
import { VueperSlides, VueperSlide } from 'vueperslides'
import 'vueperslides/dist/vueperslides.css'
import project1 from "../assets/img/engine1.jpg"
import project2 from "../assets/img/engine2.jpg"

export default {
	components: {
        VueperSlides,
         VueperSlide,
	
	},

    data: () => ({
  slides: [
  {
     image:project1
   
  },
  {
       image:project2
   
  },
  // Other slides.
]
})
};

</script>

