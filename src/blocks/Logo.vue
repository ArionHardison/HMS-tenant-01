<template>
    <div class="header-logo">
        <router-link @click.native="closeModals" :class="'logo logo-secondary transform-scale-h ' + linkClass" title="Logo" to="/">
            <img :src="'assets/img/logo/logo-' + logoColor + '.svg'" alt="Logo">
        </router-link>
    </div>
</template>

<script>
    export default {
        name: 'Logo',
        props: ['logoColor', 'linkClass'],
                computed: {
            currentPage() {
                return this.$route.path;
            },
            showMenuModal () {
                return this.$store.state.showMenuModal
            },
            showSearchModal () {
                return this.$store.state.showSearchModal
            }
        },
        methods: {
            closeModals: function() {
                if (this.currentPage === '/') {
                    if (this.showSearchModal) {
                        const searchModal = document.getElementById('search-modal');
                        searchModal.classList.remove( 'show' );
                        setTimeout(() => this.$store.commit( 'closeSearchModal' ), 150 );
                    }
                    if (this.showMenuModal) {
                        this.$store.commit( 'closeMenuModal' );
                        
                    }
                } else {
                    return;
                }

                this.$store.commit( 'variablesNull' );
            }
        }
    }
</script>
