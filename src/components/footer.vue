<template>
    <div class="footer-main">
        <div class="footer-inner">
            <!--FOOTER HEADER---------------------------------------->
            <div class="footer-inner-header">
                <div class="footer-inner-header1">
                    <span class="foot-call"> <Icon icon="healthicons:call-centre" /></span>
                       
                        <span class="foot-inner-text">
                            <h2>24/7 Clients Support</h2>
                            <h5>Our clients can reach out to us 24/7</h5>

                        </span>
                </div>

                <div class="footer-inner-header2">
                    <span class="foot-idea">  <Icon icon="icons8:idea" /></span>
                  
                     <span class="foot-inner-text">
                            <h2>Professional Touch</h2>
                            <h5>We provide that professional touch that delivers excellent services
                            </h5>
                        </span>
                </div>

                <div class="footer-inner-header3">
                    <span class="foot-shield"><Icon icon="uil:shield-check" /></span>
                   
                     <span class="foot-inner-text">
                            <h2>Quality comes first</h2>
                            <h5>We ensure to use the best methods and materials when rendering our services</h5>

                        </span>
                </div>
            </div>
            <!--------------------------------------------------------------------->


            <!--FOOTER CONTENT---------------------------------------------->
            <div class="footer-content-main">
                <div class="footer-section1 footer-sections">
                    <img src="../assets/img/logo-2.png" alt="" srcset="">
                    <p class="footer-section1-text">
                      Services Limited (SCEL) renders engineering procurement and construction, marine services and manpower supply to the oil and gas industry.
                    </p>
                    <span class="footer-section1-icon">
                        <Icon icon="ei:sc-facebook" class="foot-sec1-icon" />
                        <Icon icon="jam:instagram" class="foot-sec1-icon" />
                        <Icon icon="entypo-social:twitter" class="foot-sec1-icon" />
                        <Icon icon="foundation:social-linkedin" class="foot-sec1-icon" />
                    </span>
                </div>

                

                <div class="footer-section3 footer-sections">
                    <h2>Newsletter</h2>

                    <h3>
                        Subscribe our Newsletter 
                    </h3>
                    <div>
                        <input type="email" name="" id="" placeholder="enter your email">
                        <Icon icon="simple-icons:minutemailer" class="newslettr-icon" />
                    </div>
                   
                </div>

                <div class="footer-section4 footer-sections">
                    <h2>Get In Touch</h2>
                    <div class="foot-get-in-touch">
                        <span class="in-touch-icon"><Icon icon="eva:phone-call-outline" /></span>
                        <span class="in-touch-contact">
                            Phone Number<br/>
                            <a href="tel:+90 845 758 145">+90 845 758 145</a>
                        </span>
                    </div>

                    <div class="foot-get-in-touch">
                         <span class="in-touch-icon"><Icon icon="mdi:email-newsletter" /></span>
                        <span class="in-touch-contact">
                            Email Address<br/>
                            <a href="mailto:industo@gmail.com">industo@gmail.com</a>
                        </span>
                    </div>

                    <div class="foot-get-in-touch">
                         <span class="in-touch-icon"><Icon icon="codicon:home" /></span>
                        <span class="in-touch-contact" >               
                            Office Address<br/>
                            <address>15/C, Yang Tower, NYC</address>
                        </span>
                    </div>
                </div>

            </div>
            <!---------------------------------------------------------------------->

            <div class="footer-section-last">
                <span>
                     ©&nbsp;2022&nbsp;Stoke & Caldwell. All rights reserved
                </span>

               
            </div>

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