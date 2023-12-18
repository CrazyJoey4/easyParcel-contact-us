<script setup>
import BugReport from './BugReport.vue';
import PackagingReport from './Packaging.vue';
import GeneralReport from './GeneralReport.vue';
</script>

<template>
    <div id="main_button" class="row cu_quest d-flex">
        <div class="col-xs-12 col-sm-4 col-lg-fifth">
            <a id="shipmentEnquiry" class="btn btn-default btn-lg btn-block btn-enquiry guest-btn p-4"
                @click="toggleSelected('shipmentEnquiry')">

                <strong class="btnTitle">Shipment <br>Enquiry</strong>
                <br>
                <span class="fs-14 text-secondary toppadding-xs bottompadding-xs">Need assistance with your
                    shipments</span>
                <span class="fs-12 color">Contact Support Team <i class="material-icons list-icon fs-14"
                        style="font-weight: 900; margin-bottom: 2px;">arrow_forward</i></span>
            </a>
        </div>
        <div class="col-xs-12 col-sm-4 col-lg-fifth">
            <a id="paymentEnquiry" class="btn btn-default btn-lg btn-block btn-enquiry guest-btn p-4"
                @click="toggleSelected('paymentEnquiry')">

                <strong class="btnTitle">Payment <br>Enquiry</strong>
                <br>
                <span class="fs-14 text-secondary toppadding-xs bottompadding-xs">Having questions on your
                    payments</span><small class="fs-12 color">Contact Support Team <i class="material-icons list-icon fs-14"
                        style="font-weight: 900; margin-bottom: 2px;">arrow_forward</i></small>
            </a>
        </div>
        <div class="col-xs-12 col-sm-4 col-lg-fifth">
            <a id="salesEnquiry" class="btn btn-default btn-lg btn-block btn-enquiry p-4" data-filter=".sales"
                tag="Sale Enquiry" @click="toggleSelected('salesEnquiry')">

                <strong class="btnTitle">Sales <br>Enquiry</strong>
                <br>
                <span class="fs-14 text-secondary toppadding-xs bottompadding-xs">Talk
                    to a member of our sales team</span><small class="fs-12 color">Contact Sales Team <i
                        class="material-icons list-icon fs-14"
                        style="font-weight: 900; margin-bottom: 2px;">arrow_forward</i></small>
            </a>
        </div>
        <div class="col-xs-12 col-sm-4 col-lg-fifth">
            <a id="partnershipEnquiry" class="btn btn-default btn-lg btn-block btn-enquiry p-4" tag="Marketing Enquiry"
                @click="toggleSelected('partnershipEnquiry')">

                <strong class="btnTitle">Partnership <br>Enquiry</strong>
                <br>
                <span class="fs-14 text-secondary toppadding-xs bottompadding-xs">Start a partnerships
                    opportunities</span><small class="fs-12 color">Contact Partnerships Team <i
                        class="material-icons list-icon fs-14"
                        style="font-weight: 900; margin-bottom: 2px;">arrow_forward</i></small>
            </a>
        </div>
        <div class="col-xs-12 col-sm-4 col-lg-fifth">
            <a id="generalEnquiries" class="btn btn-default btn-lg btn-block btn-enquiry p-4" data-filter=".other_topic"
                tag="General Enquiry" @click="toggleSelected('generalEnquiries')">

                <strong class="btnTitle">Other <br>Enquiries</strong>
                <br>
                <span class="fs-14 text-secondary toppadding-xs bottompadding-xs">Having other topic to talk about or
                    suggestion</span><span class="fs-12 color">Contact Us Now <i class="material-icons list-icon fs-14"
                        style="font-weight: 900; margin-bottom: 2px;">arrow_forward</i></span>
            </a>
        </div>
    </div>

    <div class="col-md-12 topmargin divcenter text-center clearfix other_topic" style="display: none;">
        <h3>Select Your Enquiry</h3>
        <a id="BugReportFrom" class="btn btn-default btn-lg btn-enquiry btn-enquiry-step2 p-4 rightmargin-sm"
            data-filter=".bugs" tag="Bugs Report" @click="SecondtoggleSelected('BugReportFrom')">

            Bugs Report
            <br><span class="fs-12 color">Click Here <i class="material-icons list-icon fs-14"
                    style="font-weight: 900; margin-bottom: 2px;">arrow_forward</i></span>
        </a>
        <a id="PackagingReportFrom" class="btn btn-default btn-lg btn-enquiry btn-enquiry-step2 p-4 rightmargin-sm"
            data-filter=".packaging" tag="Packaging" @click="SecondtoggleSelected('PackagingReportFrom')">
            Packaging
            <br><span class="fs-12 color">Click Here <i class="material-icons list-icon fs-14"
                    style="font-weight: 900; margin-bottom: 2px;">arrow_forward</i></span>
        </a>
        <a id="GeneralReportFrom" class="btn btn-default btn-lg btn-enquiry btn-enquiry-step2 p-4" data-filter=".cust"
            tag="Customer Care" @click="SecondtoggleSelected('GeneralReportFrom')">

            General Enquiry/Feedback
            <br><span class="fs-12 color">Click Here <i class="material-icons list-icon fs-14"
                    style="font-weight: 900; margin-bottom: 2px;">arrow_forward</i></span>
        </a>
    </div>

    <div class="col-md-8 topmargin divcenter template_section BugReportFrom" style="display: none;">
        <div class="panel">
            <div class="panel-body topmargin-sm">
                <div id="general_option_template">
                    <BugReport />
                </div>
            </div>
        </div>
    </div>

    <div class="col-md-8 topmargin divcenter template_section PackagingReportFrom" style="display: none;">
        <div class="panel">
            <div class="panel-body topmargin-sm">
                <div id="general_option_template">
                    <PackagingReport />
                </div>
            </div>
        </div>
    </div>

    <div class="col-md-8 topmargin divcenter template_section GeneralReportFrom" style="display: none;">
        <div class="panel">
            <div class="panel-body topmargin-sm">
                <div id="general_option_template">
                    <GeneralReport />
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    methods: {
        toggleSelected(id) {
            const buttons = document.querySelectorAll('.btn-enquiry');
            buttons.forEach(button => button.classList.remove('selected'));

            const selectedButton = document.getElementById(id);
            selectedButton.classList.add('selected');

            if (id == 'generalEnquiries') {
                const targetElement = document.querySelector('.other_topic');

                targetElement.style.display = 'block';

                targetElement.scrollIntoView({
                    behavior: 'smooth',
                    block: 'center',
                    inline: 'nearest',
                });
            } else {
                const targetElement = document.querySelector('.other_topic');
                targetElement.style.display = 'none';
            }
        },

        SecondtoggleSelected(id) {
            const buttons = document.querySelectorAll('.btn-enquiry');
            buttons.forEach(button => button.classList.remove('selected'));

            const selectedButton = document.getElementById(id);
            selectedButton.classList.add('selected');

            if (id == 'BugReportFrom') {
                const targetElement = document.querySelector('.BugReportFrom');

                targetElement.style.display = 'block';

                targetElement.scrollIntoView({
                    behavior: 'smooth',
                    block: 'center',
                    inline: 'nearest',
                });
            } else {
                const targetElement = document.querySelector('.BugReportFrom');
                targetElement.style.display = 'none';
            }

            if (id == 'PackagingReportFrom') {
                const targetElement = document.querySelector('.PackagingReportFrom');

                targetElement.style.display = 'block';

                targetElement.scrollIntoView({
                    behavior: 'smooth',
                    block: 'center',
                    inline: 'nearest',
                });
            } else {
                const targetElement = document.querySelector('.PackagingReportFrom');
                targetElement.style.display = 'none';
            }

            if (id == 'GeneralReportFrom') {
                const targetElement = document.querySelector('.GeneralReportFrom');

                targetElement.style.display = 'block';

                targetElement.scrollIntoView({
                    behavior: 'smooth',
                    block: 'center',
                    inline: 'nearest',
                });
            } else {
                const targetElement = document.querySelector('.GeneralReportFrom');
                targetElement.style.display = 'none';
            }
        }
    }
};
</script>

<style scoped>
.color {
    color: var(--theme-pink);
    font-size: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 3px;
}

.d-flex {
    display: flex;
    flex-wrap: wrap;
    gap: 30px;
    justify-content: space-between;

    font-family: Lato, "Helvetica Neue", "Open Sans", Arial, sans-serif;
}

.cu_quest.d-flex .btn-enquiry {
    height: 100%;
    max-width: 204px;
}

.cu_quest>div>a.btn {
    white-space: normal;
}

.btn {
    display: inline-block;
    text-align: center;
    vertical-align: middle;
    -ms-touch-action: manipulation;
    touch-action: manipulation;
    cursor: pointer;
    border: 1px solid var(--grey-soft);
    white-space: nowrap;
    padding: 20px;
    border-radius: 4px;
}

.btn-default {
    color: var(--dark-grey);
    background-color: var(--white);
}

.rightmargin-sm {
    margin-right: 30px !important;
}

.btn-default:hover {
    color: #333;
    background-color: #e6e6e6;
    border-color: #adadad;
}

.btn-enquiry .text-secondary {
    display: block;
}

.fs-14 {
    font-size: 14px !important;
}

.btnTitle {
    font-size: 18px;
    font-weight: 700;
}

.text-secondary {
    color: #868e96 !important;
}

.bottompadding-xs {
    padding-bottom: 15px !important;
}

.toppadding-xs {
    padding-top: 15px !important;
}

.btn-enquiry.selected,
.btn-enquiry.selected .text-secondary,
.btn-enquiry.selected .color,
.btn-enquiry-step2.selected,
.btn-enquiry-step2.selected .text-secondary,
.btn-enquiry-step2.selected .color {
    color: #fff !important;
}

.btn-enquiry.selected,
.btn-enquiry-step2.selected {
    border-color: var(--theme-pink);
    box-shadow: rgb(249 39 142 / 50%) 0 4px 12px;
    background-color: var(--theme-pink);
}

/* Enquiry Form */
h3 {
    color: #000;
    font-weight: 600;
    line-height: 1.5;
    margin: 0 0 30px;
}

.text-center {
    text-align: center !important;
}

.divcenter {
    float: none !important;
    margin-left: auto !important;
    margin-right: auto !important;
}

.topmargin {
    margin-top: 50px !important;
}

.panel {
    margin-bottom: 20px;
    background-color: #fff;
    border: 1px solid transparent;
    border-radius: 4px;
    -webkit-box-shadow: 0 1px 1px rgba(0, 0, 0, .05);
    box-shadow: 0 1px 1px rgba(0, 0, 0, .05);
    max-width: 750px;

    font-family: Lato, "Helvetica Neue", "Open Sans", Arial, sans-serif;

}

.topmargin-sm {
    margin-top: 30px !important;
}

.panel-body {
    padding: 15px;
}

#general_option_template {
    position: relative !important;
}

/* Responsive */
@media (min-width: 992px) {
    .col-md-8 {
        width: 66.66666667%;
    }
}

@media only screen and (min-width: 992px) {
    .col-md-12 {
        width: 100%;
    }

    .btn-enquiry-step2 {
        width: initial;
    }
}
</style>
