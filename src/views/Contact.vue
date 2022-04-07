<template>
    <div>
        <aside class="text-center bg-gradient-primary-to-secondary">
            <div class="container px-5">
                <div class="row gx-5 justify-content-center">
                    <div class="col-xl-8">
                        <div class="h2  text-white mb-3">" Need a software developer? "</div>
                    </div>
                </div>
            </div>
        </aside>
        <section id="contact" class="projects contact">
            <div class="container">
                <div class="projects-wrapper contact-wrapper row">
                    <div class="contact-top text-left col-lg-6 col-sm-12 mb-6">
                        <div class="section-heading pt-3 ">
                            <h1 class="title text-dark">Let's work together</h1>
                        </div>
                        <div class="address-list">
                            <div class="address">
                                <h5 class="title text-dark">Mail</h5>
                                <h6 class="lead text-dark"><a href="mailto:haydentan27@gmail.com">haydentan27@gmail.com</a></h6>
                            </div>
                            <div class="address">
                                <h5 class="title text-dark">Location</h5>
                                <h6 class="lead text-dark">Kuala Lumpur, Malaysia</h6>
                            </div>
                            <div class="address">
                                <h5 class="title text-dark">Phone</h5>
                                <h6 class="lead text-dark">+60163099552</h6>
                            </div>
                        </div>
                    </div>
                    <div class="contact-form-box col-lg-6 col-xs-10 mb-6">
                        <h2 class="title">Describe your project</h2>
                        <form role="form" method="POST" @submit.prevent="sendEmail">
                            <div class="form-group">
                                <label class="leadLabel">Name</label>
                                <input type="text" name="name" class="form-control" placeholder="Jane Tan" v-model="nameMsg" @blur="$v.nameMsg.$touch()" validator="$v.nameMsg" />
                            </div>
                            <div class="error" v-if="$v.nameMsg.$error">
                                <div>
                                    <div v-if="!$v.nameMsg.required">* Name cannot be empty.</div>
                                </div>
                            </div>
                            <div class="form-group">
                                <label class="leadLabel">Email</label>
                                <input type="email" name="_replyto" class="form-control" placeholder="example@gmail.com" v-model="emailMsg" @blur="$v.emailMsg.$touch()" validator="$v.emailMsg" />
                            </div>
                            <div class="error" v-if="$v.emailMsg.$error">
                                <div>
                                    <div v-if="!$v.emailMsg.required">* Email cannot be empty.</div>
                                    <div v-if="$v.emailMsg.required && !$v.emailMsg.email">* Invalid email address.</div>
                                </div>
                            </div>
                            <div class="form-group">
                                <label class="leadLabel">How can I help you?</label>
                                <textarea name="message" rows="3" class="form-control" placeholder="Message" v-model="messageMsg" @blur="$v.messageMsg.$touch()" validator="$v.messageMsg"></textarea>
                            </div>
                            <div class="error" v-if="$v.messageMsg.$error">
                                <div>
                                    <div v-if="!$v.messageMsg.required">* Message cannot be empty.</div>
                                </div>
                            </div>
                            <div class="form-group">
                                <button type="submit" class="btn btn-primary text-white submit-btn">
                                    <span class="d-flex align-items-center">
                                        <i class="bi bi-envelope-fill me-3"></i>
                                        <span class="small">Send</span>
                                    </span>
                                </button>
                            </div>
                            <div v-if="loadingTxt">
                                <p class="mb-8 text-primary">Delivering your email...</p>
                            </div>
                            <div v-if="status" :class="[status != 'Successfully delivered. Thanks'? 'form-err': 'form-success']" class="msg">{{status}}</div>
                        </form>
                    </div>
                </div>
            </div>
        </section>
    </div>
</template>
<script>
    import axios from 'axios'
    import { required, email } from 'vuelidate/lib/validators'

    export default {
        data() {
            return {
                nameMsg: '',
                emailMsg: '',
                messageMsg: '',
                loadingTxt: false,
                status: null
            }
        },
        methods: {
            sendEmail() {
                this.$v.$touch();
                if (this.$v.$invalid) {
                    return;
                }

                this.loadingTxt = true;

                axios({
                    url: 'https://formspree.io/f/mvolbwle',
                    data: {
                        name: this.nameMsg,
                        from: this.emailMsg,
                        _subject: `${this.nameMsg} | Friendly Message from Github Page`,
                        message: this.messageMsg,
                    },
                    method: 'POST',
                    responseType: 'arraybuffer', // important
                }).then((response) => {
                    if (response.status == "200") {
                        this.status = "Successfully delivered. Thanks"
                    }
                    this.loadingTxt = false;
                    this.reset();
                }).catch((error) => {
                    if (error.response) {
                        this.status = "Opps! There are some problems, try again later."
                    }
                });

            },
            reset() {
                this.nameMsg = '';
                this.emailMsg = '';
                this.messageMsg = '';
                this.$v.$reset();
            }
        },
        validations: {
            nameMsg: { required },
            emailMsg: { required, email },
            messageMsg: { required }

        }
    }


</script>
<style>
    .form .container {
        width: 90%;
        max-width: 500px;
        margin: 0 auto;
        padding: 20px;
        box-shadow: 0px 0px 20px #00000010;
        background-color: white;
        border-radius: 8px;
        margin-bottom: 20px;
    }

    .form-group {
        width: 100%;
        margin-top: 20px;
        font-size: 20px;
    }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 5px;
            font-size: 18px;
            border: 1px solid rgba(128, 128, 128, 0.199);
            margin-top: 5px;
        }

    textarea {
        resize: vertical;
    }

    button[type="submit"] {
        width: 100%;
        border: none;
        outline: none;
        padding: 20px;
        font-size: 24px;
        border-radius: 8px;
        font-family: "Montserrat";
        color: rgb(27, 166, 247);
        text-align: center;
        cursor: pointer;
        margin-top: 10px;
        transition: 0.3s ease background-color;
    }

        button[type="submit"]:hover {
            background-color: rgb(214, 226, 236);
        }

    #status {
        width: 90%;
        max-width: 500px;
        text-align: center;
        padding: 10px;
        margin: 0 auto;
        border-radius: 8px;
    }

        #status.success {
            background-color: rgb(211, 250, 153);
            animation: status 4s ease forwards;
        }

        #status.error {
            background-color: rgb(250, 129, 92);
            color: white;
            animation: status 4s ease forwards;
        }

    @keyframes status {
        0% {
            opacity: 1;
            pointer-events: all;
        }

        90% {
            opacity: 1;
            pointer-events: all;
        }

        100% {
            opacity: 0;
            pointer-events: none;
        }
    }

    .form-err {
        background-color: orangered;
        animation: status 4s ease forwards;
    }

    .form-success {
        background-color: mediumspringgreen;
        animation: status 4s ease forwards;
    }

    .msg {
        margin-top: 8px;
        text-align: center;
        font-family: "Kanit", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
    }
</style>