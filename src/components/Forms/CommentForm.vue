<template>
    <form v-on:submit.prevent="submitForm" id="commentform" class="comment-form">
        <div class="form-group form-group-sm">
            <p class="comment-notes">Your email address will not be published. Required fields are marked
                <span class="required">*</span>
            </p>
        </div>

        <div class="form-group form-group-xs">
            <textarea v-model="form.comment" id="comment" class="form-control form-control-lg" name="comment" cols="45" rows="6" placeholder="Comment *" required="required"></textarea>
        </div>

        <div class="form-group form-group-xs">
            <input v-model="form.author" id="comment-author" class="form-control form-control-lg" name="comment-author" type="text" placeholder="Name *" required="required">
        </div>

        <div class="form-group form-group-xs">
            <input v-model="form.email" id="comment-email" class="form-control form-control-lg" name="comment-email" type="email" placeholder="Email *" required="required">
        </div>

        <div class="form-group form-group-sm">
            <input v-model="form.url" id="comment-url" class="form-control form-control-lg" name="comment-url" placeholder="Website" type="url">
        </div>

        <div class="form-group form-group-sm">
            <p class="comment-form-cookies-consent custom-control custom-checkbox">
                <input id="wp-comment-cookies-consent" class="custom-control-input" name="wp-comment-cookies-consent" type="checkbox" value="yes">
                <label class="custom-control-label" for="wp-comment-cookies-consent">Save my name, email, and website in this browser for the next time I comment.</label>
            </p>
        </div>

        <div class="form-submit">
            <input name="submit" type="submit" class="btn btn-outline-secondary" value="Post Comment">
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
        name: 'CommentForm',
        data() {
            return {
                form: {
                    comment: '',
                    author: '',
                    email: '',
                    url: ''
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
