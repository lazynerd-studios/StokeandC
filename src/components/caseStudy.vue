<template>
    <div>
        <div class="case-study-inner1">
            <div class="study-inner1-title">Industo Case Study</div>
            <h2>Recent Industry Project</h2>
        </div>

        <div class="case-study-slider-main">
            <div class="case-study-slide1">
                    <h3>
                        Machinary Agile Motive Frameworks
                    </h3>

                    <p>
                        In standard machining, a skilled machinist operates equipment, removing or developing steel.
                         This is done as per the requirement given by designers and developers.
                    </p>

                      <button class="case-btn">Case Details<Icon icon="ant-design:plus-outlined" class="case-button-icon" /></button>
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
import { Icon } from '@iconify/vue';

export default {
	components: {
        VueperSlides,
         VueperSlide,
		Icon,
	},

    data: () => ({
  slides: [
  {
     image: require('@/assets/project-1-670x570.jpg')
   
  },
  {
       image: require('@/assets/image-b.jpg')
   
  },
  // Other slides.
]
})
};

</script>

