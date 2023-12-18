<template>
    <div class="row">
        <div class="promo promo-border bottommargin-sm" style="background-color: #fff;">
            <h4 class="nobottommargin">Preferable reaching to us via live chat? No problem</h4>
            <span class="text-secondary">Best responding at 10am - 6pm, GMT+8, Mon - Fri</span>
            <a onclick="window.fcWidget.open();" class="button livebtn">Live Chat</a>
        </div>
    </div>
</template>

<script>
export default {

};
</script>

<style scoped>
h4 {
    color: var(--black);
    font-weight: 600;
    font-size: 18px;
    font-family: Lato, "Helvetica Neue", "Open Sans", Arial, sans-serif;
    margin: 0;
}

.row {
    padding-top: 50px;
    width: 100%;
    margin-left: auto;
    margin-right: auto;

    font-family: Lato, "Helvetica Neue", "Open Sans", Arial, sans-serif;
    color: var(--black);
}

.promo.promo-border {
    border: 1px solid #E5E5E5;
    border-radius: 3px;
    padding-left: 30px;
}

.promo {
    position: relative;
    padding: 30px 200px 30px 0;
}

.bottommargin-sm {
    margin-bottom: 30px !important;
}

.text-secondary {
    color: var(--grey-mute) !important;
    display: block;
    color: #000;
    font-weight: 300;
    font-size: 16px;
    margin-top: 6px;
}

.promo.promo-border a.button {
    right: 30px;
}

.promo a.button {
    position: absolute;
    top: 50%;
    margin: -18px 0 0;
    left: auto;
    right: 0;
}

body:not(.device-touch) .button {
    -webkit-transition: all .2s ease-in-out;
    -o-transition: all .2s ease-in-out;
    transition: all .2s ease-in-out;
}

.button {
    display: inline-block;
    cursor: pointer;
    white-space: nowrap;
    margin: 5px;
    font-size: 14px;
    height: 40px;
    text-transform: uppercase;
    letter-spacing: 1px;
    padding: 0 22px;
}

.livebtn {
    color: var(--theme-pink);
    border: 2px solid var(--theme-pink);
    background-color: transparent;
    line-height: 36px;
    font-weight: 600;
    border-radius: 3px;
}

.livebtn:hover {
    background-color: var(--theme-dark-pink);
    color: #FFF;
    border-color: transparent !important;
    text-shadow: 1px 1px 1px rgba(0, 0, 0, .2);
}

@media (min-width: 992px) {
    .col-md-12 {
        width: 100%;
    }
}
</style>
