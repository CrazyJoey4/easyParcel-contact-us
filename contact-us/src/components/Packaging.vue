<template>
    <div class="packaging row">
        <div class="col-md-12">
            <h4 class="mb-0">Packaging</h4>
            <hr>
            <div class="panel panel-default">
                <div class="panel-heading">
                    <h5 class="mb-0">These articles may help you</h5>
                    <a href="https://helpcentre-my.easyparcel.com/support/home" target="_blank" class="panel-link">Search
                        More <i class="material-icons list-icon fs-14"
                            style="font-weight: 900; margin-bottom: 2px">arrow_forward</i></a>
                </div>
                <div class="panel-body">
                    <ul>
                        <li><a href="https://helpcentre-my.easyparcel.com/support/solutions/articles/9000188903-how-should-i-pack-my-parcels-"
                                target="_blank">How should I pack my parcels? <i class="material-icons list-icon fs-14"
                                    style="font-weight: 900;">arrow_forward</i></a></li>
                        <li><a href="https://helpcentre-my.easyparcel.com/support/solutions/articles/9000188604-where-can-i-purchase-packaging-materials-on-easyparcel-"
                                target="_blank">Where can i purchase packaging materials on EasyParcel? <i
                                    class="material-icons list-icon fs-14" style="font-weight: 900;">arrow_forward</i></a>
                        </li>
                        <li><a href="https://helpcentre-my.easyparcel.com/support/solutions/articles/9000188605-how-to-claim-free-packing-materials-"
                                target="_blank">How to claim free packing materials? <i
                                    class="material-icons list-icon fs-14" style="font-weight: 900;">arrow_forward</i></a>
                        </li>
                        <li><a href="https://helpcentre-my.easyparcel.com/support/solutions/articles/9000224205-how-can-i-implement-quality-check-after-packaging-done-"
                                target="_blank">How can I implement quality check after packaging done? <i
                                    class="material-icons list-icon fs-14" style="font-weight: 900;">arrow_forward</i></a>
                        </li>
                    </ul>
                </div>
            </div>
            <form class="form-horizontal text-left" @submit.prevent="submitForm">
                <div class="form-group">
                    <label class="col-sm-3 nott">Title<span class="text-danger">*</span></label>
                    <div class="col-sm-9">
                        <input type="text" class="sm-form-control" value="" name="title" maxlength="50"
                            placeholder="State the subject / topic of your enquiries here....">
                        <div class="err_msg" style="color:#F00;">{{ titleError }}</div>
                    </div>
                </div>
                <div class="form-group">
                    <label class="col-sm-3 nott">Registered Email Address<small class="question_tooltip"
                            data-toggle="tooltip" data-placement="top" title=""
                            data-original-title="Kindly fill in the registered email address you wish to receive the reply from us."><i
                                class="material-icons list-icon" style="font-size: 12px;">help_outline</i></small><span
                            class="text-danger">*</span>
                    </label>
                    <div class="col-sm-9">
                        <input type="email" class="sm-form-control" value="" name="Customer_Email"
                            placeholder="Registered Email Address">
                        <div class="err_msg" style="color:#F00;">{{ emailError }}</div>
                    </div>
                </div>
                <div class="form-group">
                    <label class="col-sm-3 nott">Issue/Comment<span class="text-danger">*</span></label>
                    <div class="col-sm-9">
                        <textarea class="sm-form-control" name="comment" maxlength="3000"
                            placeholder="Leave your message here...."></textarea>
                        <div class="err_msg" style="color:#F00;">{{ commentError }}</div>
                    </div>
                </div>
                <div class="form-group">
                    <label class="col-sm-3 nott">Tracking / Order No<small class="question_tooltip" data-toggle="tooltip"
                            data-placement="top" title="" data-original-title="EI-XXXX"><i class="material-icons list-icon"
                                style="font-size: 12px;">help_outline</i></small><span class="text-danger">*</span></label>
                    <div class="col-sm-9">
                        <input type="text" class="sm-form-control" value="" name="awb" maxlength="30">
                        <div class="err_msg" style="color:#F00;">{{ awbError }}</div>
                        <p class="small m-0 text-muted"><span class="text-danger">*</span>Submit 1 tracking no / order no at
                            a time</p>
                    </div>
                </div>
                <div class="form-group">
                    <label class="col-sm-3 nott">Attachments</label>
                    <div class="col-sm-9">
                        <div class="contactform_dropzone dropzone dz-clickable" id="packaging_attachment">

                            <div class="dz-message" data-dz-message=""> <span> <small class="text-info"><i
                                            class="material-icons list-icon fs-50 text-info">image</i><br>
                                        Click <em>or</em> Drop files here to upload</small> </span>
                            </div>
                        </div>
                        <p class="small text-center m-0">Individual file size limit 2MB. File support: png, jpg, pdf.</p>
                        <input name="attachments" value="" type="hidden">
                    </div>
                </div>
                <hr>
                <div class="form-group">
                    <div class="col-sm-offset-4 col-sm-4">
                        <button type="button" class="button button-3d button-rounded button-pink nomargin nott btn-block"
                            @click="submitForm">Submit Now</button>
                    </div>
                </div>
            </form>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            titleError: '',
            emailError: '',
            commentError: '',
            awbError: '',
        };
    },
    methods: {
        async submitForm() {
            this.titleError = '';
            this.emailError = '';
            this.commentError = '';
            this.awbError = '';

            const title = this.$el.querySelector('input[name="title"]').value;
            const email = this.$el.querySelector('input[name="Customer_Email"]').value;
            const awb = this.$el.querySelector('input[name="awb"]').value;
            const comment = this.$el.querySelector('textarea[name="comment"]').value;

            if (!title.trim()) {
                this.titleError = 'You must enter a title without any special characters.';
            }

            const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            if (!email.trim()) {
                this.emailError = 'You must enter your registered email address.';
            } else if (!emailPattern.test(email)) {
                this.emailError = 'You must enter a valid registered email address.';
            }

            if (!comment.trim()) {
                this.commentError = 'You must enter your comment for us to understand your problem.';
            }

            if (!awb.trim()) {
                this.awbError = 'You must key in AWB / Order ID.';
            }

            if (this.titleError || this.emailError || this.commentError || this.awbError) {
                return;
            }

            console.log('Form submitted:', { title, email, comment });

            this.titleError = '';
            this.emailError = '';
            this.commentError = '';
            this.awbError = '';

            this.simulateServerProcessing(title, email, comment);
        },

        simulateServerProcessing(title, email, comment) {
            // Simulate sending email
            console.log('Simulating server processing:', { title, email, comment });

            // Simulate a successful response
            setTimeout(() => {
                this.$el.querySelector('form').reset();
                alert('Form submitted successfully. Thank you!');
            }, 1000);
        }
    }
};
</script>

<style scoped>
h4, h5 {
    font-size: 18px;
    font-weight: 600;
    font-family: Lato, "Helvetica Neue", "Open Sans", Arial, sans-serif;
    margin: 0;
}

h5 {
    font-size: 14px;
    font-weight: 700;
}

a {
    text-decoration: none;
    color: var(--theme-pink);
    font-size: 14px;
}

.mb-0 {
    margin-bottom: 0 !important;
}

.text-left {
    text-align: left;
}

form {
    margin-bottom: 30px;
}

.text-danger {
    color: #a94442;
}

.err_msg {
    font-size: 14px;
    font-family: Lato, "Helvetica Neue", "Open Sans", Arial, sans-serif;
}

/* Panel */
.panel-default {
    border-color: #ddd;
}

.panel {
    margin-bottom: 20px;
    background-color: #fff;
    border: 1px solid transparent;
    border-radius: 4px;
    -webkit-box-shadow: 0 1px 1px rgba(0, 0, 0, .05);
    box-shadow: 0 1px 1px rgba(0, 0, 0, .05);
}

.panel-default>.panel-heading {
    color: #333;
    background-color: #f2f4f8;
    border: 1px solid #ddd;

    padding: 10px 15px;
    border-top-right-radius: 3px;
    border-top-left-radius: 3px;
}

.panel-default .panel-body {
    background-color: #f2f4f8;
    border: 1px solid #ddd;
    padding: 15px;
}

.panel-heading {
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.panel .panel-body ul {
    padding-left: 15px;
    margin-bottom: 0;
}

/* Input Form */
.form-group {
    margin-bottom: 15px;
    display: flex;
    gap: 10px;
    justify-content: center;
}

label {
    display: inline-block;
    font-size: 13px;
    font-weight: 700;
    font-family: Lato, "Helvetica Neue", "Open Sans", Arial, sans-serif;
    letter-spacing: 1px;
    color: #555;
    margin-bottom: 10px;
    cursor: pointer;
}

.sm-form-control {
    display: block;
    width: 100%;
    padding: 8px 14px;
    font-size: 15px;
    line-height: 1.42857143;
    color: #555;
    background-color: #fff;
    background-image: none;
    border: 2px solid #DDD;
    border-radius: 0 !important;
    -webkit-transition: border-color ease-in-out .15s;
    -o-transition: border-color ease-in-out .15s;
    transition: border-color ease-in-out .15s;
    height: auto;
}

.dropzone.dz-clickable {
    cursor: pointer;
}

.dropzone {
    border: 2px dotted rgba(0, 0, 0, 0.3);
    min-height: 150px;
    background: white;
    padding: 20px 20px;
}

.dropzone .dz-message {
    text-align: center;
    margin: 2em 0;
}

.text-center {
    text-align: center !important;
}

.m-0 {
    margin: 0 !important;
}

small,
.small {
    font-size: 80%;
    font-weight: 400;
}

.text-info {
    color: #31708f;

}

.material-icons {
    font-family: 'Material Icons';
    font-weight: normal;
    font-style: normal;
    font-size: 15px !important;
    line-height: 1;
    letter-spacing: normal;
    text-transform: none;
    display: inline-block;
    white-space: nowrap;
    word-wrap: normal;
    direction: ltr;
    -webkit-font-feature-settings: 'liga';
    -webkit-font-smoothing: antialiased;
}

textarea {
    overflow: auto;
    resize: block;
}

.button.button-3d {
    border-radius: 3px;
    background-color: var(--theme-pink);
    color: var(--white);
    font-weight: 600;
    letter-spacing: 1px;

    display: inline-block;
    position: relative;
    cursor: pointer;
    outline: 0;
    white-space: nowrap;
    padding: 0 22px;
    font-size: 14px;
    height: 40px;
    line-height: 40px;
    width: 100%;
    outline: none;
    border: none;

    transition: all .2s ease-in-out;
}

.button.button-3d:hover {
    background-color: var(--theme-dark-pink);
}

/* Responsive */
@media (min-width: 768px) {
    .col-sm-3 {
        width: 25%;
    }

    .col-sm-4 {
        width: 33.33333333%;
    }

    .col-sm-9 {
        width: 75%;
    }
}

@media only screen and (max-width: 767px) {
    .form-group {
        flex-wrap: wrap;
        gap: 0;
    }

    .col-sm-3,
    .col-sm-4,
    .col-sm-9 {
        width: 100%;
    }

    label {
        font-size: 12px;
    }

    .button.button-3d {
        font-size: 12px;
    }

    .dropzone {
        padding: 10px;
    }
}
</style>
