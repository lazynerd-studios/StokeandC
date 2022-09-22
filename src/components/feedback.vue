<template>
    <div class="feeback-main">
        <div class="feeback-inner">

    <div class="feeback-inner1">
        <div class="feedback-title">Customer Feedback</div>
        <h2>Our Happy Customers Say About</h2>
        <div class="feedback-cards-main">
                <div class="feedback-cards-inner">
                    <div class="feed-cards">
                        <span class="feed-cards-text">
                            <h1>500k</h1>
                            <h5>Completed Project</h5>
                        </span>
                        <span class="feed-icon-main">
                            <Icon icon="tabler:checklist" class="feed-card-icon" />
                        </span>
                    </div>
                    <div class="feed-cards">
                         <span class="feed-cards-text">
                              <h1>2,000</h1>
                            <h5>Running Project</h5>
                         </span>
                        <span class="feed-icon-main">
                            <Icon icon="tabler:checklist"  class="feed-card-icon"/>
                        </span>
                    </div>
                </div>

                <div class="feedback-cards-inner">
                    <div class="feed-cards">
                         <span class="feed-cards-text">
                              <h1>110+</h1>
                            <h5>Expert Team</h5>
                         </span>
                        <span class="feed-icon-main">
                            <Icon icon="clarity:group-line" class="feed-card-icon" />
                        </span>
                    </div>
                    <div class="feed-cards">
                         <span class="feed-cards-text">
                              <h1>50+</h1>
                            <h5>Wining Awards</h5>
                         </span>
                        <span class="feed-icon-main">
                            <Icon icon="tabler:checklist" class="feed-card-icon" />
                        </span>
                    </div>
                </div>

        </div>
    </div>    

    <div class="feeback-inner2">

        
  <vue-carousel :data="data"  direction="up" :controls="false" :autoplay="false">
  
  </vue-carousel>
  


    </div>

    </div>
    </div>
</template>


<script>
import { Icon } from '@iconify/vue';
import VueCarousel from '@chenfengyuan/vue-carousel';

    export default {
	components: {
        VueCarousel,
		Icon,
	},
    data() {
     return{
          data: [
        <div class="slide1">

        <div class="slides slides1">
        <Icon icon="ci:double-quotes-l" class="feed-quotes" />
        <div class="feed-slide-title">
        <span class="feed-slide-title1">
         In this world there are companies that are all business and you know what they do, and then there are companies like Industo who not only deliver.
        </span>
        <span class="feed-dash-img">
        <img src={require('../assets/img/f-slide1.jpg')} alt="" srcset="" class="feed-slide-img"/>
        </span>
        </div>

        <div class="feed-slide-subtitle">
        <h1 class="feed-slid-subtitle-text">Bonnie Tolbert</h1>
        <div class="meta-star">
         <label>Rating</label>
         <span class="item-star five-star">
         <Icon icon="dashicons:star-filled" class="feed-star" />
         <Icon icon="dashicons:star-filled" class="feed-star" />
         <Icon icon="dashicons:star-filled" class="feed-star" />
         <Icon icon="dashicons:star-filled" class="feed-star" />
         <Icon icon="dashicons:star-filled" class="feed-star" />
          </span>
          </div>
        </div>
        
        </div>

        <div class="slides slides2">

         <Icon icon="ci:double-quotes-l" class="feed-quotes"/>
        <div class="feed-slide-title">
        <span class="feed-slide-title1">
         In this world there are companies that are all business and you know what they do, and then there are companies like Industo who not only deliver.
        </span>
        <span class="feed-dash-img">
        <img src={require('../assets/img/f-slide2.jpg')} alt="" srcset="" class="feed-slide-img"/>
        </span>
        </div>

        <div class="feed-slide-subtitle">
        <h1 class="feed-slid-subtitle-text">Bonnie Tolbert</h1>
        <div class="meta-star">
         <label>Rating</label>
         <span class="item-star five-star">
         <Icon icon="dashicons:star-filled" class="feed-star" />
         <Icon icon="dashicons:star-filled" class="feed-star" />
         <Icon icon="dashicons:star-filled" class="feed-star" />
         <Icon icon="dashicons:star-filled" class="feed-star" />
         <Icon icon="dashicons:star-filled" class="feed-star" />
          </span>
          </div>
        </div>

        </div>

        </div>,

        <div class="slide2">

        <div class="slides slides3">
        
             <Icon icon="ci:double-quotes-l" class="feed-quotes" />
        <div class="feed-slide-title">
        <span class="feed-slide-title1">
         In this world there are companies that are all business and you know what they do, and then there are companies like Industo who not only deliver.
        </span>
        <span class="feed-dash-img">
        <img src={require('../assets/img/f-slide3.jpg')} alt="" srcset="" class="feed-slide-img"/>
        </span>
        </div>

        <div class="feed-slide-subtitle">
        <h1 class="feed-slid-subtitle-text">Bonnie Tolbert</h1>
        <div class="meta-star">
         <label>Rating</label>
         <span class="item-star five-star">
         <Icon icon="dashicons:star-filled" class="feed-star"/>
         <Icon icon="dashicons:star-filled" class="feed-star" />
         <Icon icon="dashicons:star-filled" class="feed-star" />
         <Icon icon="dashicons:star-filled" class="feed-star" />
         <Icon icon="dashicons:star-filled" class="feed-star" />
          </span>
          </div>
        </div>

        </div>

        <div class="slides slides4">

                 <Icon icon="ci:double-quotes-l" class="feed-quotes"/>
        <div class="feed-slide-title">
        <span class="feed-slide-title1">
         In this world there are companies that are all business and you know what they do, and then there are companies like Industo who not only deliver.
        </span>
        <span class="feed-dash-img">
        <img src={require('../assets/img/f-slide1.jpg')} alt="" srcset="" class="feed-slide-img"/>
        </span>
        </div>

        <div class="feed-slide-subtitle">
        <h1 class="feed-slid-subtitle-text">Bonnie Tolbert</h1>
        <div class="meta-star">
         <label>Rating</label>
         <span class="item-star five-star">
         <Icon icon="dashicons:star-filled" class="feed-star" />
         <Icon icon="dashicons:star-filled"class="feed-star" />
         <Icon icon="dashicons:star-filled"class="feed-star" />
         <Icon icon="dashicons:star-filled" class="feed-star" />
         <Icon icon="dashicons:star-filled" class="feed-star" />
          </span>
          </div>
        </div>

        </div>

        </div>,
       
      ],
     }
  },
};

</script>

<style>
.slide {
  align-items: center;
  color: #fff;
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin-bottom: 10px;
}
.feed-quotes{
    border-radius: 50%;
    font-size: 47px;
    background-color: rgba(174, 172, 255, 0.862);
    color: rgb(85, 83, 248);
}
.feed-slide-title{
 width: 100%;
 display: flex;
 justify-content: space-between;
 align-items: center;
}
.feed-slide-subtitle{
    margin-top: 20px;
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.feed-dash-img{
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 10px;
    border: 2px dashed rgb(84, 84, 255);
    border-radius: 50%;
}
.meta-star > label{
    font-size: 20px;
    font-weight: 600;
    margin-right: 5px;
}
.feed-slide-title1{
    width: 400px;
   color: #666;
    font-size: 14px;
    font-weight: 600;
    line-height: 1.764;
}
.slides{
    color: black;
    height: fit-content;
    width: 100%;
  background-color: #fff;
    margin-bottom: 30px;
    border-radius: 10px;
    padding: 20px;
    box-shadow: 0 4px 10px rgb(12 12 12 / 9%);
}

.vue-carousel--down>.vue-carousel__indicators, .vue-carousel--up>.vue-carousel__indicators{
    top: 40px;
    left: 0;
    margin-left: -40px;
}
.vue-carousel__indicator:before{
    background-color:#ff8500;
    padding: 3px;
    border-radius: 5px;
}
.vue-carousel__indicator{
    margin: 0.5rem;
    
}
.feed-slide-img{
    height: 100px;
    border-radius: 50%;
}
.feed-star{
    color: gold;
}
 @media screen and (max-width: 550px){
        .feed-dash-img{
    padding: 5px;
        }

.feed-slide-img{
    height: 70px;
    border-radius: 50%;
    }

    .feed-slide-title1{
    font-size: 12px;
    }

   .feed-slid-subtitle-text{
        font-size: 20px;
    }
    .meta-star > label{
    font-size: 15px;
   
}

.vue-carousel--down>.vue-carousel__indicators, .vue-carousel--up>.vue-carousel__indicators{
    transform: rotate(90deg);
    top: auto;
    left: 60px;
    margin-left: -40px;
    transform-origin: 20% 40%;
    margin-top: 30px;
}

}
</style>