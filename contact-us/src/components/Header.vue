<template>
    <head>
        <link rel="stylesheet" href="https://www.w3schools.com/w3css/4/w3.css">
        <link rel="stylesheet" href="https://fonts.googleapis.com/icon?family=Material+Icons">
    </head>

    <header :class="{ 'sticky-header': isHeaderSticky }" id="header">
        <div class="logo">
            <a href="https://easyparcel.com/my/en" class="standard-logo retina-logo"
                data-dark-logo="https://s3.ap-southeast-1.amazonaws.com/easyparcel-static/Public/source/general/img/menu-logo/easyparcel_logo.png"
                alt="EasyParcel Logo">

                <img src="https://s3.ap-southeast-1.amazonaws.com/scontent.easyparcel.com/pcm/image/general/easyparcel_logo2-my.png"
                    srcset="https://s3.ap-southeast-1.amazonaws.com/scontent.easyparcel.com/pcm/image/general/easyparcel_logo2-my.png 1x, https://s3.ap-southeast-1.amazonaws.com/scontent.easyparcel.com/pcm/image/general/easyparcel_logo2-my@2.png 2x"
                    alt="EasyParcel Logo">
            </a>
        </div>

        <nav id="primary-menu">
            <ul class="sf-js-enabled" style="touch-action: pan-y;">
                <li class="sub-menu">
                    <a href="#" class="sf-with-ul">
                        <div class="nav-menu">Send Parcel<font-awesome-icon icon="angle-down" /></div>
                    </a>
                    <ul class="submenu-options" style="display: none;">
                        <li>
                            <a href="https://easyparcel.com/my/en/quote">
                                <div>Get A Quote</div>
                            </a>
                        </li>
                        <li>
                            <a href="https://easyparcel.com/my/en/single">
                                <div>Single Parcel</div>
                            </a>
                        </li>
                        <li>
                            <a href="https://app.easyparcel.com/my/en/bulk">
                                <div>Bulk Parcel</div>
                            </a>
                        </li>
                    </ul>
                </li>

                <li id="services" class="sub-menu">
                    <a href="#" class="sf-with-ul">
                        <div class="nav-menu">Features<font-awesome-icon icon="angle-down" /></div>
                    </a>

                    <div class="mega-menu-content clearfix" style="display: none;">
                        <div class="megaWrap features">
                            <ul class="mega-menu-column col-md-4 col-sm-6" style="">

                                <li><a href="https://easyparcel.com/my/en/domestic">
                                        <div>Domestic Delivery</div>
                                    </a></li>
                                <li><a href="https://easyparcel.com/my/en/international">
                                        <div>International Delivery</div>
                                    </a></li>
                                <li><a href="https://easyparcel.com/my/en/on-demand-delivery">
                                        <div>On-Demand Delivery</div>
                                    </a></li>
                                <li><a href="https://easyparcel.com/my/en/cash-on-delivery">
                                        <div>Cash On Delivery</div>
                                    </a></li>
                                <li><a href="https://blog.easyparcel.com/my/international-shipment-with-ddp-ddu/">
                                        <div>Duties &amp; Taxes Visibility</div>
                                    </a></li>
                            </ul>
                            <ul class="mega-menu-column col-md-4 col-sm-6" style="">
                                <li><a href="https://easyparcel.com/my/en/integration-list/quicksned">
                                        <div>QuickSend</div>
                                    </a>
                                </li>
                                <li><a href="https://easyparcel.com/my/en/shop/buy">
                                        <div>EasyParcel Shop</div>
                                    </a>
                                </li>
                                <li><a href="https://easyparcel.com/my/en/easyparcel-reward">
                                        <div>EasyParcel Reward</div>
                                    </a>
                                </li>
                                <li><a href="https://easyparcel.com/my/en/referral">
                                        <div>Referral</div>
                                    </a>
                                </li>
                            </ul>
                            <ul class="mega-menu-column col-md-4 col-sm-6" style="">
                                <li><a
                                        href="https://blog.easyparcel.com/my/new-feature-quickreturn-click-go-steps-for-customers-to-book-for-returned-parcel/">
                                        <div>Marketing Tools</div>
                                    </a></li>
                                <hr class="hr-no-margin hidden-sm hidden-xs">
                                <li><a href="">
                                        <div class="sub-nav">Custom Branding</div>
                                    </a>
                                    <div class="sub-link">
                                        <a href="https://easyparcel.com/my/en/sms-tracking">Custom Tracking SMS</a>
                                        <a href="https://easyparcel.com/my/en/email-tracking">Custom Tracking Email</a>
                                        <a href="https://easyparcel.com/my/en/awb-branding">AWB Branding</a>
                                        <a href="https://easyparcel.com/my/en/easytrack-branding">EasyTrack Branding</a>
                                    </div>
                                </li>
                                <li>
                                    <a href="">
                                        <div class="sub-nav">Manage Campaign</div>
                                    </a>
                                    <div class="sub-link">
                                        <a href="https://easyparcel.com/my/en/sms-tracking">SMS Campaign</a>
                                    </div>
                                </li>
                                <li class="notHover">
                                    <div class="easycover-feature-box">
                                        <p style="margin-bottom: 0">EasyCover</p>
                                        <p style="margin-bottom: 0; font-size: 12px;">Secure your shipment from loss with a
                                            maximum of RM10,000 coverage.</p>
                                        <div class="easycover-feature-right-arrow">
                                            <a href="https://easyparcel.com/my/en/easycover">
                                                <i class="material-icons">arrow_forward</i>
                                            </a>
                                        </div>
                                    </div>
                                </li>
                                <li class="notHover">
                                    <a href="" class="view-all-link">View All Features
                                        <i class="material-icons">arrow_forward</i>
                                    </a>
                                </li>
                            </ul>
                        </div>
                    </div>
                </li>

                <li class="sub-menu"><a href="#" class="sf-with-ul">
                        <div class="nav-menu">Integration<font-awesome-icon icon="angle-down" /></div>
                    </a>
                    <ul class="submenu-options" style="display: none;">
                        <li><a href="https://easyparcel.com/my/en/integration-list">
                                <div>Shipping Integration</div>
                            </a></li>
                        <li><a href="https://easyparcel.com/my/en/couriers">
                                <div>Our Couriers</div>
                            </a></li>
                        <li><a href="https://easyparcel.com/my/en/partnerships">
                                <div>Our Partners</div>
                            </a></li>
                    </ul>
                </li>

                <li>
                    <a href="https://easyparcel.com/my/en/promotion">
                        <div class="nav-menu">Pricing</div>
                    </a>
                </li>

                <li class="sub-menu"><a href="#" class="sf-with-ul">
                        <div class="nav-menu">About<font-awesome-icon icon="angle-down" /></div>
                    </a>
                    <ul class="submenu-options" style="display: none;">
                        <li><a href="https://easyparcel.com/my/en/about-us">
                                <div>About Us</div>
                            </a></li>
                        <li><a href="https://easyparcel.com/my/en/career">
                                <div>Career</div>
                            </a></li>
                        <li><a href="https://easyparcel.com/my/en/testimonials">
                                <div>Testimonials</div>
                            </a></li>
                        <li><a href="https://easyparcel.com/my/en/brand-guidelines">
                                <div>Brand Guidelines</div>
                            </a></li>
                    </ul>
                </li>

                <li class="sub-menu"><a href="#" class="sf-with-ul">
                        <div class="nav-menu">Resources<font-awesome-icon icon="angle-down" /></div>
                    </a>
                    <div class="mega-menu-content style-2 clearfix" style="display: none;">
                        <div class="megaWrap resources">
                            <ul class="mega-menu-column col-sm-6">
                                <li><a href="http://easyparcel.com/blog/my">
                                        <div>Blog</div>
                                    </a></li>
                                <li><a href="https://easyparcel.com/my/en/country-guides">
                                        <div>Country Guides</div>
                                    </a></li>
                                <li><a href="https://app.easyparcel.com/my/en/contact-us/">
                                        <div>Contact Us</div>
                                    </a></li>
                                <li><a href="http://helpcentre-my.easyparcel.com/support/home">
                                        <div>Help Center</div>
                                    </a></li>
                                <li><a href="https://easyparcel.com/my/en/apilanding">
                                        <div>Developers &amp; Api</div>
                                    </a></li>
                            </ul>

                            <ul class="mega-menu-column col-sm-6">
                                <li>
                                    <a href="#">
                                        <div>Tool/Widget</div>
                                    </a>
                                </li>
                                <li>
                                    <a href="https://app.easyparcel.com/my/en/account/address-book">
                                        <div class="div-padding-left">Address Box</div>
                                    </a>
                                </li>
                                <li>
                                    <a href="https://easyparcel.com/my/en/quote">
                                        <div class="div-padding-left">Rate Checker</div>
                                    </a>
                                </li>
                                <li>
                                    <a href="https://app.easyparcel.com/my/en/account/calculator">
                                        <div class="div-padding-left">Volumetric Calculator</div>
                                    </a>
                                </li>
                                <li>
                                    <a href="https://app.easyparcel.com/my/en/account/taxcalculator">
                                        <div class="div-padding-left">Tax Calculator</div>
                                    </a>
                                </li>
                                <li>
                                    <a href="https://easyparcel.com/my/en/easytrack">
                                        <div class="div-padding-left">EasyTrack</div>
                                    </a>
                                </li>
                            </ul>
                        </div>
                    </div>
                </li>

            </ul>
        </nav>

        <div class="nav_button_wrap">
            <button class="nav_button loginbtn">
                <a href="https://app.easyparcel.com/my/en/login/">
                    <div>Login</div>
                </a>
            </button>
            <button class="nav_button signbtn">
                <a href="https://app.easyparcel.com/my/en/login/">
                    <div>Sign Up For Free</div>
                </a>
            </button>
        </div>

    </header>
</template>

<script>
export default {
    data() {
        return {
            isHeaderSticky: false
        };
    },
    mounted() {
        window.addEventListener('scroll', this.handleScroll);
    },
    beforeDestroy() {
        window.removeEventListener('scroll', this.handleScroll);
    },
    methods: {
        handleScroll() {
            this.isHeaderSticky = window.scrollY > 0;
        },
        handleResize() {
            this.isHeaderSticky = window.innerWidth >= 922 && window.scrollY > 0;
        }
    }
};
</script>

<style scoped>
a {
    text-decoration: none;
    color: var(--theme-pink);

}

header {
    background-color: #fff;
    min-height: 100px;
    display: flex;
    align-items: center;
    justify-content: center;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);

    font-family: Lato, "Helvetica Neue", "Open Sans", Arial, sans-serif;
    z-index: 99;
}

.sticky-header {
    box-shadow: rgba(0, 0, 0, 0.1) 0px 6px 8px 2px;
    position: sticky;
    top: 0;
    background-color: #FFF;
    box-shadow: rgba(0, 0, 0, 0.1) 0px 6px 8px 2px;
    transition: 0.3s ease-in-out;
}

svg.svg-inline--fa.fa-angle-down {
    font-size: 11px;
}

.logo img {
    max-height: 100px;
}

nav ul {
    list-style: none;
    margin: 0;
    padding: 0;
    transition: 0.3s opacity;
}

nav li {
    display: inline-block;
    padding: 0px 25px;
}

nav a {
    text-decoration: none;
    letter-spacing: 1px;
}

.nav-menu {
    display: flex;
    align-items: center;
    gap: 6px;
}

#primary-menu {
    display: grid;
    float: left;
    padding: 20px 0;
}

#primary-menu ul li>a {
    font-size: 14px;
    color: #000;
    text-transform: none;
    font-weight: 700;
}

.submenu-options,
.mega-menu-content {
    display: none;
    position: absolute;
    background-color: #fff;
    box-shadow: 0 13px 42px 11px rgba(0, 0, 0, .05);
    border: 1px solid var(--white-soft);
    width: 220px;
    height: auto;
    z-index: 199;
    transition: opacity 0.3s ease;
}

.nav-menu:hover {
    color: #000000;
    border-bottom: 2px solid var(--theme-pink);
}

.sub-menu>ul li {
    display: flex;
    font-size: 12px;
    font-weight: bold;
    padding: 10px 20px;
}

#primary-menu ul ul li a {
    color: #666;
}

#primary-menu ul li>a {
    padding: 0px 20px;
}

#primary-menu ul ul li:hover,
#primary-menu ul ul li:hover>a {
    background-color: var(--white-soft);
    color: var(--theme-pink);

    -webkit-transition: all .2s ease-in-out;
    -o-transition: all .2s ease-in-out;
    transition: all .2s ease-in-out;
}


/* Mega Menu */
.mega-menu-content {
    position: absolute;
    background-color: #fff;
    box-shadow: 0 13px 42px 11px rgba(0, 0, 0, .05);
    border: 1px solid var(--white-soft);
    width: 1000px;
    max-width: 100%;
    height: auto;
    z-index: 199;
    margin-left: -150px;
    padding: 15px;
}

.megaWrap {
    display: flex;
    gap: 5px;
}

.style-2 {
    width: 720px;
    max-width: 400px;
    margin: 0 -5px;
}

.mega-menu-column {
    width: 100%;
}

ul.mega-menu-column.col-sm-6 {
    padding: 0 15px;
}

ul.mega-menu-column.col-sm-6:not(:first-child) {
    border-left: 1px solid #F2F2F2;
}

.mega-menu-content ul li {
    display: flex;
    flex-direction: column;
    padding: 10px 0;
}

.mega-menu-content li li a {
    color: var(--theme-pink) !important;
}

.sub-menu:hover .submenu-options,
.sub-menu:hover .mega-menu-content {
    display: block !important;
}

#primary-menu ul li#services .mega-menu-content {
    max-width: 1000px;
    width: 1000px;
    margin-left: -300px;
    padding-top: 15px;
    padding-bottom: 15px;
}

.sub-link {
    margin-left: 50px;
    font-size: 14px;
    display: flex;
    flex-direction: column;
}

.sub-link a {
    color: var(--theme-pink) !important;
}

.easycover-feature-right-arrow {
    display: flex;
    justify-content: right;
}

.easycover-feature-box {
    background-image: url(https://easyparcel.s3.amazonaws.com/Public/source/general/img/general/2023-09/MY-easycover-feature-box.png);
    padding: 5px 20px;
    padding-left: 100px;
    background-repeat: no-repeat;
    background-size: contain;
    color: #ffffff !important;
    margin: 13px 10px;
    width: calc(100% - 30px);
    max-width: 300px;
}

.easycover-feature-right-arrow a i {
    color: #ffffff !important;
    font-size: 30px !important;
    font-weight: 900 !important;
}

li .view-all-link:hover {
    background-color: red;
}

.view-all-link {
    padding: 10px 20px !important;
    color: rgb(249, 39, 142) !important;
    border-radius: 3px;

    display: flex;
    align-items: center;
    justify-content: flex-start;
}

.view-all-link:hover {
    background-color: rgb(249, 39, 142) !important;
    color: #ffffff !important;
}

.notHover:hover {
    background-color: var(--white) !important;
}

/* Navigation Button */
.nav_button_wrap {
    display: flex;
    gap: 5px;
    justify-content: space-between;

    font-family: Lato, "Helvetica Neue", "Open Sans", Arial, sans-serif;
    font-weight: 600;
}

.nav_button {
    font-size: 12px;
    min-width: 72px;
    max-width: 80px;
    min-height: 46px;

    padding: 0px 17px !important;
    height: auto !important;

    color: var(--theme-pink);
    border: 2px solid #000;
    border-color: var(--theme-pink);
    background-color: transparent;
    border-radius: 3px;

    -webkit-transition: all .2s ease-in-out;
    -o-transition: all .2s ease-in-out;
    transition: all .2s ease-in-out;
}

.nav_button a {
    letter-spacing: 1px;
}

.signbtn {
    min-width: 80px;
    max-width: 80px;
    padding: 0px 10px !important;
    height: auto !important;
    background-color: var(--theme-pink) !important;
}

.signbtn a {
    color: var(--white) !important;
}

.nav_button:hover,
.nav_button:hover a {
    background: var(--theme-pink);
    color: var(--white);
    text-shadow: none;
}

.signbtn:hover {
    border-color: var(--theme-dark-pink) !important;
    background-color: var(--theme-dark-pink) !important;
}


/* Responsive styles */
@media only screen and (max-width: 922px) {
    #header.sticky-header {
        position: relative;
        box-shadow: none;
    }

    #primary-menu {
        display: none;
    }

    .nav_button_wrap {
        display: none;
    }

    .logo {
        max-width: 100%;
        text-align: center;
        padding: 20px 0;
    }
}

@media only screen and (max-width: 768px) {
    header {
        min-height: 80px;
    }

    .nav-menu {
        gap: 3px;
    }

    nav li {
        padding: 0px 15px;
    }

    .mega-menu-content,
    .style-2 {
        width: 100%;
        margin-left: 0;
    }

    .mega-menu-column {
        width: 100%;
        padding: 0 15px;
        border-left: none;
    }

    .sub-link {
        margin-left: 0;
    }

    .easycover-feature-box {
        padding-left: 20px;
        width: 100%;
    }

    .nav_button_wrap {
        flex-direction: column;
    }

    .nav_button,
    .signbtn {
        min-width: auto;
        max-width: none;
    }

    .view-all-link {
        padding: 10px 15px !important;
    }
}
</style>


