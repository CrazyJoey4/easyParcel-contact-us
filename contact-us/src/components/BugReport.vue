<template>
    <div class="bugs row">
        <div class="col-md-12">
            <h4 class="mb-0">Bugs Report</h4>
            <hr>
            <form class="form-horizontal text-left" @submit.prevent="submitForm">
                <div class="form-group">
                    <label class="col-sm-3">Title<span class="text-danger">*</span></label>
                    <div class="col-sm-9">
                        <input type="text" class="sm-form-control" value="" name="title" maxlength="50"
                            placeholder="State the subject / topic of your enquiries here....">
                        <div class="err_msg" style="color:#F00;">{{ titleError }}</div>
                    </div>
                </div>
                <div class="form-group">
                    <label class="col-sm-3">Registered Email Address<small class="question_tooltip" data-toggle="tooltip"
                            data-placement="top" title=""
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
                    <label class="col-sm-3">Question/Comment<span class="text-danger">*</span></label>
                    <div class="col-sm-9">
                        <textarea class="sm-form-control" name="comment" maxlength="3000"
                            placeholder="Leave your message here...."></textarea>
                        <div class="err_msg" style="color:#F00;">{{ commentError }}</div>
                    </div>
                </div>
                <div class="form-group">
                    <label class="col-sm-3">Attachments</label>
                    <div class="col-sm-9">
                        <div class="contactform_dropzone dropzone dz-clickable" id="bugs_attachment">

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
                        <button type="button" class="button button-3d button-rounded button-pink nomargin btn-block"
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
        };
    },
    methods: {
        async submitForm() {
            this.titleError = '';
            this.emailError = '';
            this.commentError = '';

            const title = this.$el.querySelector('input[name="title"]').value;
            const email = this.$el.querySelector('input[name="Customer_Email"]').value;
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

            if (this.titleError || this.emailError || this.commentError) {
                return;
            }

            console.log('Form submitted:', { title, email, comment });

            this.titleError = '';
            this.emailError = '';
            this.commentError = '';

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
h4 {
    font-size: 18px;
    font-weight: 600;
    font-family: Lato, "Helvetica Neue", "Open Sans", Arial, sans-serif;
    margin: 0;
}

.err_msg {
    font-size: 14px;
    font-family: Lato, "Helvetica Neue", "Open Sans", Arial, sans-serif;
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

textarea {
    overflow: auto;
    resize: block;
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

    .col-sm-1,
    .col-sm-2,
    .col-sm-3,
    .col-sm-4,
    .col-sm-5,
    .col-sm-6,
    .col-sm-7,
    .col-sm-8,
    .col-sm-9,
    .col-sm-10,
    .col-sm-11,
    .col-sm-12 {
        float: left;
    }

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
