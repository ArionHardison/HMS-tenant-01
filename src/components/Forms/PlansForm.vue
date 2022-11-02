<template>
    <form v-on:submit.prevent="submitForm" id="cf-2" class="contact-form">
        <div class="form-group form-group-xs">
            <input v-model="form.firstName" name="cf-2-first-name" type="text" class="form-control form-control-lg" id="cf-2-first-name" placeholder="First name *" required="required">
        </div>

        <div class="form-group form-group-xs">
            <input v-model="form.lastName" name="cf-2-last-name" type="text" class="form-control form-control-lg" id="cf-2-last-name" placeholder="Last name *" required="required">
        </div>

        <div class="form-group form-group-xs">
            <input v-model="form.email" name="cf-2-email" type="email" class="form-control form-control-lg" id="cf-2-email" placeholder="Email *" required="required">
        </div>

        <div class="form-group form-group-xs">
            <input v-model="form.company" name="cf-2-company" type="text" class="form-control form-control-lg" id="cf-2-company" placeholder="Company *" required="required">
        </div>

        <div class="form-group form-group-xs">
            <input v-model="form.phone" name="cf-2-phone-no" type="text" class="form-control form-control-lg" id="cf-2-phone-no" placeholder="Phone no. *" required="required">
        </div>

        <div class="form-group form-group-sm">
            <textarea v-model="form.message" name="cf-2-message" class="form-control form-control-lg" id="cf-2-message" placeholder="Message *" required="required"></textarea>
        </div>

        <div class="form-group form-group-xs">
            <button type="submit" class="btn btn-outline-tertiary">Submit</button>
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
        name: 'PlansForm',
        data() {
            return {
                form: {
                    firstName: '',
                    lastName: '',
                    email: '',
                    company: '',
                    phone: '',
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
