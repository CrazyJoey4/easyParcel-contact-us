<template>
    <div class="heading-block">
        <h3 class="cookie-font capitalize color">Contact Us</h3>
        <span class="text-secondary">Swing by our <a href="https://helpcentre-my.easyparcel.com/support/home"
                target="_blank">Help Centre</a> to find some immediate answers
            <br>
            Or let us know your questions by choosing one of the topics below
        </span>
    </div>
</template>

<script>
export default {

};
</script>

<style scoped>
h3 {
    font-weight: 600;
    font-size: 26px;
    font-family: Lato, "Helvetica Neue", "Open Sans", Arial, sans-serif;
}

a {
    text-decoration: none !important;
    color: var(--theme-pink);
}

.capitalize {
    text-transform: capitalize !important;
}

.color {
    color: var(--theme-pink);
}

.text-secondary {
    font-family: Lato, "Helvetica Neue", "Open Sans", Arial, sans-serif;
    color: #868e96 !important;
    font-size: 20px;
    font-weight: 300;
}

.heading-block {
    text-align: center;
    margin-bottom: 50px !important;
    line-height: 1.5;
}

.heading-block>span {
    max-width: 700px;
    margin-left: auto;
    margin-right: auto;
}

.heading-block>span:not(.before-heading) {
    display: block;
    margin-top: 10px;
    font-weight: 300;
    color: #666;
}

.heading-block:after {
    content: '';
    display: block;
    margin-top: 30px;
    width: 40px;
    border-top: 2px solid #000;
    margin-left: auto;
    margin-right: auto;
}
</style>
