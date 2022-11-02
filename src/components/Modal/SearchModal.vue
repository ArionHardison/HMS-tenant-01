<template>
    <fragment>
        <transition @enter="startTransitionModal" @after-enter="endTransitionModal" @before-leave="endTransitionModalLeave" @after-leave="startTransitionModalLeave">
            <div id="search-modal" class="modal fade" v-show="$store.getters.showSearchModal" ref="modal">
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
                                            <div class="search-close-toggle">
                                                <button @click="closeModal" type="button" class="btn btn-lg btn-outline-tertiary btn-round p-0 min-w-auto" data-dismiss="modal" aria-label="Close">
                                                    <i class="fas fa-times"></i>
                                                </button>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>

                            <div class="modal-body modal-body-centered">
                                <form class="search-form" role="search" method="get" :action="urlAction">
                                    <div class="search input-group">
                                        <input class="form-control form-control-lg" type="text" placeholder="Search" name="s">

                                        <div class="input-group-append">
                                            <button type="submit" class="btn btn-link border-0 p-0 min-w-auto">
                                                <i class="fas fa-search"></i>
                                            </button>
                                        </div>
                                    </div>
                                </form>
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
    import Languages from '../../blocks/General/Languages';
    import { Fragment } from 'vue-fragment';

    export default {
        name: 'Search-Modal',
        components: {
            'logo-block': Logo,
            'languages-block': Languages,
            Fragment
        },
        data() {
            return {
                urlAction: window.location.origin + this.$router.resolve( {
                    name: 'search-results',
                    params: { id: 1 }
                } ).href 
            }
        },
        props: ['logoClass'],
        methods: {
            toggleSearchModal: function( event ) {
                this.$store.commit( 'toggleSearchModal' )
            },
            closeModal() {
                document.getElementById( 'search-modal' ).classList.remove( 'show' );

                setTimeout(() => this.$store.commit( 'closeSearchModal' ), 150 );
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
            if ( document.body.classList.contains( 'modal-open' ) ) {
                document.body.classList.remove( 'modal-open' )
            }

            document.removeEventListener( 'keydown', e => {
                if ( e.isComposing || e.keyCode === 27) {
                    this.closeModal();
                }
            });

            this.$store.commit( 'variablesNull' );
        }
    }
</script>
