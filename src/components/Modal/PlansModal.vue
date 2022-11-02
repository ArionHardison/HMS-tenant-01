<template>
    <fragment>
        <transition @enter="startTransitionModal" @after-enter="endTransitionModal" @before-leave="endTransitionModalLeave" @after-leave="startTransitionModalLeave">
            <div id="plans-modal" class="modal fade" v-show="$store.getters.showPlansModal" ref="modal">
                <div class="modal-dialog modal-full" role="document">
                    <div class="wrapper">
                        <div class="modal-content">
                            <div class="modal-header modal-header-top">
                                <div class="header-content d-flex justify-content-between w-100">
                                    <div class="header-left align-self-center">
                                        <logo-block logo-color="light" />
                                    </div>

                                    <div class="header-right d-flex justify-content-end">
                                        <div class="d-flex align-items-center">
                                            <div class="plans-close-toggle">
                                                <button @click="closeModal" type="button" class="btn btn-lg btn-outline-tertiary btn-round p-0 min-w-auto" data-dismiss="modal" aria-label="Close">
                                                    <i class="fas fa-times"></i>
                                                </button>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                            <div class="modal-body modal-body-centered">
                                <div class="plans-modal-content">
                                    <h3 class="modal-t-head after">Order
                                        <span class="modal-title-result"> {{ $store.getters.orderText }}</span>
                                    </h3>

                                    <plans-form-component />
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </transition>

        <div class="modal-backdrop fade d-none" ref="backdrop"></div>
    </fragment>
</template>

<script>
    import PlansForm from '../Forms/PlansForm';
    import Logo from '../../blocks/Logo';
    import { Fragment } from 'vue-fragment';

    export default {
        name: 'Plans-Modal',
        components: {
            'plans-form-component': PlansForm,
            'logo-block': Logo,
            Fragment
        },
        data() {
            return {
                showModal: false
            }
        },
        methods: {
            togglePlansModal: function( event ) {
                this.$store.commit( 'togglePlansModal', '' )
            },
            closeModal() {
                document.getElementById( 'plans-modal' ).classList.remove( 'show' );

                setTimeout(() => this.$store.commit( 'closePlansModal' ), 150 );
            },
            startTransitionModal() {
                if ( ! this.$refs.backdrop.classList.contains( 'd-block' ) ) {
                    this.$refs.backdrop.classList.add( 'd-block' );
                }

                if ( ! this.$refs.modal.classList.contains( 'd-block' ) ) {
                    this.$refs.modal.classList.add( 'd-block' );
                }
            },
            startTransitionModalLeave() {
                if ( this.$refs.backdrop.classList.contains( 'd-block' ) ) {
                    this.$refs.backdrop.classList.remove( 'd-block' );
                }

                if ( this.$refs.modal.classList.contains( 'd-block' ) ) {
                    this.$refs.modal.classList.remove( 'd-block' );
                }
            },
            endTransitionModal() {
                if ( ! this.$refs.backdrop.classList.contains( 'show' ) ) {
                    this.$refs.backdrop.classList.add( 'show' );
                }

                if ( ! this.$refs.modal.classList.contains( 'show' ) ) {
                    this.$refs.modal.classList.add( 'show' );
                }

                if ( ! document.body.classList.contains( 'modal-open' ) ) {
                    document.body.classList.add( 'modal-open' )
                }
            },
            endTransitionModalLeave() {
                if ( this.$refs.backdrop.classList.contains( 'show' ) ) {
                    this.$refs.backdrop.classList.remove( 'show' );
                }

                if ( this.$refs.modal.classList.contains( 'show' ) ) {
                    this.$refs.modal.classList.remove( 'show' );
                }

                if ( document.body.classList.contains( 'modal-open' ) ) {
                    document.body.classList.remove( 'modal-open' )
                }
            }
        },
        mounted() {
            document.addEventListener( 'keydown', e => {
                if ( e.isComposing || e.keyCode === 27) {
                    this.closeModal();
                }
            });
        },
        beforeDestroy() {
            document.removeEventListener( 'keydown', e => {
                if ( e.isComposing || e.keyCode === 27) {
                    this.closeModal();
                }
            });

            this.$store.commit( 'variablesNull' );
        }
    }
</script>
