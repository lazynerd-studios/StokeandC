<template>
    <div class="faq-main">

    <div class="faq1">
        <div>Frequently Asked Questions</div>
        <h2>Get Every Single Answer From Here</h2>
        <img src="../assets/img/14331.jpg" alt="" srcset="">
    </div>    

    <div class="container">
<p>
    Working with several word press themes and templates the last years, I only can say this is the best in every level. I use it for my company and the reviews that I have already are all excellent.
</p>

<div>
  <input type="checkbox" id="question17" name="q"  class="questions">
  <div class="plus">+</div>
  <label for="question17" class="question">
What are industrial visuals?
  </label>
  <div class="answers">
    <p>Industrial visuals are images that depict or represent various elements regarding the manufacturing of products via factory workers or industrial automation. Images can include workers on assembly lines, aerial shots of factories, and industrial design blueprints. </p>
    
  </div>
</div>
<!-- _____________________________________________________ --> 
<div>
  <input type="checkbox" id="question18" name="q"  class="questions">
  <div class="plus">+</div>
  <label for="question18" class="question">
How to choose engaging industrial images?
  </label>
  <div class="answers">
    <p>With so many industrial images in the Shutterstock library, it’s important to narrow down the selection to images that offer the most impact and value for your project. Images with people are a good choice, especially if they are engaged in an activity that is easily understandable by the viewer. Such images have a higher chance of standing out and catching a viewer’s attention.</p>
    
  </div>
</div>
<!-- _____________________________________________________ --> 
<div>
  <input type="checkbox" id="question19" name="q"  class="questions">
  <div class="plus">+</div>
  <label for="question19" class="question">
How to find high-quality industrial images?
  </label>
  <div class="answers">
    <p>High-quality industrial images are easy to find on Shutterstock. To start the process, type what you’re looking for in the Shutterstock search bar. In this case, you type “industrial” in the search bar. If you’re not able to find what you’re looking for or you want to narrow down your options, you can find various options on the left-hand side of the search results page. </p>
    
  </div>
</div>
<!-- _____________________________________________________ --> 
<div>
  <input type="checkbox" id="question20" name="q" class="questions">
  <div class="plus">+</div>
  <label for="question20" class="question">
Where can you use pictures of industries and factories?
  </label>
  <div class="answers">
    <p>Images and illustrations of factories can fit within a variety of projects from internal corporate memos to advertisements and header images on webpages. Companies that may not want to take images inside. </p>
  </div>
</div>
    </div>
    </div>
</template>

<script>
const items = document.querySelectorAll(".accordion button");
var i = 0
function toggleAccordion() {
  const itemToggle = this.getAttribute('aria-expanded');
  
  for (i = 0; i < items.length; i++) {
    items[i].setAttribute('aria-expanded', 'false');
  }
  
  if (itemToggle == 'false') {
    this.setAttribute('aria-expanded', 'true');
  }
}

items.forEach(item => item.addEventListener('click', toggleAccordion));
</script>

<style scoped>
@import url(https://fonts.googleapis.com/css?family=Lato:300,400,700);


body {
  font-family: "Lato", sans-serif;
  font-size: 18px;
  background: #fff;
  line-height:26px;
}

h1 {
 font-family: "Lato", sans-serif;
font-weight: 700;
font-style: normal;
color: #98c23d;
  font-size: 32px;
  
}


.content {
  width: 80%;
  padding: 20px;
  margin: 0 auto;
  padding: 0 60px 0 0;
}

.centerplease {
  margin: 0 auto;
  max-width: 270px;
  font-size: 40px;
}

.question {
    border: 1px solid rgb(213, 213, 213);
    border-radius:5px ;
  position: relative;
  margin: 0;
  padding: 20px 10px 20px 50px;
  display: block;
  width:100%;
  cursor: pointer;
}

.answers {
  font-weight:300;
  background: #f2f2f2;
  padding: 0px 15px;
  margin: 0px 0;
  height: 0;
  overflow: hidden;
  z-index: -1;
  position: relative;
  opacity: 0;
  -webkit-transition: .7s ease;
  -moz-transition: .7s ease;
  -o-transition: .7s ease;
  transition: .7s ease;
}

.questions:checked ~ .answers{
  height: auto;
  opacity: 1;
  padding: 15px;
}

.plus {
  color:black;
  position: absolute;
  margin-left: 10px;
  margin-top: 15px;
  z-index: 5;
  font-size: 2em;
  line-height: 100%;
  -webkit-user-select: none;    
  -moz-user-select: none;
  -ms-user-select: none;
  -o-user-select: none;
  user-select: none;
  -webkit-transition: .3s ease;
  -moz-transition: .3s ease;
  -o-transition: .3s ease;
  transition: .3s ease;
}

.questions:checked ~ .plus {
  -webkit-transform: rotate(45deg);
  -moz-transform: rotate(45deg);
  -o-transform: rotate(45deg);
  transform: rotate(45deg);
}

.questions {
  display: none;
}
</style>