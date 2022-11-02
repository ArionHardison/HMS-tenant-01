<template>
    <form v-on:submit.prevent="submitForm" id="cf-1" class="contact-form">
        <div class="form-group form-group-xs">
            <input v-model="form.name" name="name" type="text" class="form-control form-control-lg bg-gray-light" id="cf-1-name" placeholder="Name" required="required">
        </div>

        <div class="form-group form-group-xs">
            <input v-model="form.email" name="email" type="email" class="form-control form-control-lg bg-gray-light" id="cf-1-email" placeholder="Email" required="required">
        </div>

        <div class="form-group form-group-xs">
            <textarea v-model="form.message" name="message" class="form-control form-control-lg bg-gray-light" id="cf-1-message" placeholder="Message" required="required"></textarea>
        </div>

        <div class="form-group form-group-xs mb-0">
            <button type="submit" class="btn btn-outline-secondary">Send Message</button>
        </div>

        <transition appear leave-active-class="animated fadeOut">
            <div v-if="callAlert" id="alert" :class="'animated fadeIn alert alert--shadow alert-' + alertClass">
                {{ responseMessage }}
            </div>
        </transition>
    </form>
</template>

<script>
    import axios from 'axios';

    export default {
        name: 'ContactsForm',
        data() {
            return {
                form: {
                    name: '',
                    email: '',
                    message: ''
                },
                successMessage: "Sender's message was sent successfully",
                warningMessage: 'Fill up the form, please!',
                errorMessage: 'Something go wrong. Try again later!',
                responseMessage: '',
                alertClass: '',
                callAlert: false
            }
        },
        methods: {
            async submitForm() {
                axios.post( 'https://store.adveits.com/API/form.php', this.form, {
                    headers: {
                        'Access-Control-Allow-Origin': '*',
                        'Content-Type': 'application/json; charset=UTF-8'
                    },
                }, ).then( response => {
                    if ( response.data.status === 'success' ) {
                        this.responseMessage = this.successMessage;
                    }

                    if ( response.data.status === 'warning' ) {
                        this.responseMessage = this.warningMessage;
                    }

                    if ( response.data.status === 'error' ) {
                        this.responseMessage = this.errorMessage;
                    }
                    this.alertClass = response.data.status;
                    this.callAlert  = true;

                    setTimeout( () => {
                        this.callAlert = false;
                    }, 2000 )
                } ).catch( error => {
                    this.responseMessage = this.errorMessage;
                    this.alertClass      = 'danger';
                    this.callAlert       = true;

                    setTimeout( () => {
                        this.callAlert = false;
                    }, 2000 )
                } );
            }
        }
    }
</script>
