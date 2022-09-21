<template>
    <div class="faq-main">

    <div class="faq1">
        <div>What We Stand For</div>
        <h2>To provide that professional touch that delivers excellent services</h2>
        
    </div>    

    <div class="container">

 <div class="do-img">
 <img src="../assets/img/engine7.jpg" alt="" srcset=""></div>


<!-- _____________________________________________________ --> 

 
</div>
<!-- _____________________________________________________ --> 
</div>
<!-- _____________________________________________________ --> 

 
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




img{
  width: 450px;
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