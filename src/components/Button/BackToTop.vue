<template>
    <div v-if="render" id="back-to-top">
        <a @click="scrollToSection(scrollTarget)" class="scroll-to-id" :href="scrollTarget"><i class="malex-icon-arrow-up"></i></a>
    </div>
</template>

<script>
    export default {
        name: 'BackToTop',
        data: () => ({ 
            render: false,
            scrollTarget: '#home-index'
        }),
        mounted() {
            if ( this.currentPage === '/404' || this.currentPage === '/ui' ) {
                this.render = false;
            } else {
                this.render = true;
            }

            if ( this.currentPage === '/' ) {
                this.scrollTarget = '#home-index';
            } else {
                this.scrollTarget = '#header';
            }
        },
        computed: {
            currentPage() {
                return this.$route.path;
            }
        }
    };
</script>
