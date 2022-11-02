<template>
    <fragment>
        <transition @enter="startTransitionModal" @after-enter="endTransitionModal" @before-leave="endTransitionModalLeave" @after-leave="startTransitionModalLeave">
            <div id="menu-modal" class="modal fade" v-show="$store.getters.showMenuModal" ref="modal">
                <div class="modal-dialog modal-full" role="document">
                    <div class="wrapper">
                        <div class="modal-content">
                            <div class="modal-header modal-header-top">
                                <div class="header-content d-flex justify-content-between w-100">
                                    <div class="header-left align-self-center">
                                        <logo-block :logo-color="logoClass" />
                                    </div>

                                    <div class="header-right d-flex justify-content-end">
                                        <div class="d-flex align-items-center">
                                            <search-modal-button-component button-class="adv-light" btn-outline="btn-outline-tertiary" />

                                            <div class="menu-close-toggle">
                                                <button @click="toggleMenuModal" type="button" class="btn btn-lg btn-outline-tertiary btn-round p-0 min-w-auto" data-dismiss="modal" aria-label="Close">
                                                    <i class="fas fa-times"></i>
                                                </button>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>

                            <div class="modal-body modal-body-centered">
                                <div class="d-flex flex-column flex-sm-row flex-md-row flex-lg-row flex-xl-row justify-content-between align-items-sm-center align-items-md-center align-items-lg-center align-items-xl-center w-100">
                                    <div class="modal-text order-1 order-sm-0 order-md-0 order-lg-0 order-xl-0">
                                        <modal-contact-info-block />
                                    </div>

                                    <transition>
                                        <div class="animated fadeInRight d-flex justify-content-end w-100 order-0 order-sm-1 order-md-1 order-lg-1 order-xl-1">
                                            <modal-menu-primary-block />
                                        </div>
                                    </transition>
                                </div>
                            </div>

                            <div class="modal-footer">
                                <div class="d-flex flex-column flex-sm-row flex-md-row flex-lg-row flex-xl-row justify-content-between w-100">
                                    <div class="modal-text">
                                        <p>© {{ new Date().getFullYear() }} Business Consulting Agency Vue JS Template By Adveits</p>
                                    </div>

                                    <languages-block />
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
    import Logo from '../../blocks/Logo';
    import { Fragment } from 'vue-fragment';
    import SearchModalButton from '../Button/SearchModalButton';
    import ModalContactInfo from '../../blocks/General/ModalContactInfo';
    import Languages from '../../blocks/General/Languages';
    import ModalMenuPrimary from '../../blocks/General/ModalMenuPrimary';

    export default {
        name: 'Menu-Modal',
        components: {
            'modal-menu-primary-block': ModalMenuPrimary,
            'languages-block': Languages,
            'modal-contact-info-block': ModalContactInfo,
            'search-modal-button-component': SearchModalButton,
            'logo-block': Logo,
            Fragment
        },
        props: ['logoClass'],
        computed: {
            currentPage() {
                return this.$route.path;
            }
        },
        methods: {
            toggleMenuModal: function( event ) {
                this.$store.commit( 'toggleMenuModal' )
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
                if ( document.getElementById( 'search-modal' ).classList.contains( 'd-block' ) ) {
                    return;
                } else if ( e.isComposing || e.keyCode === 27 ) {
                    this.$store.commit( 'closeMenuModal' );
                }
            });
        },
        beforeDestroy() {
            if ( document.body.classList.contains( 'modal-open' ) ) {
                document.body.classList.remove( 'modal-open' )
            }

            document.removeEventListener( 'keydown', e => {
                if ( e.isComposing || e.keyCode === 27 ) {
                    this.$store.commit( 'closeMenuModal' );
                }
            });

            this.$store.commit( 'variablesNull' );
        }
    }
</script>
