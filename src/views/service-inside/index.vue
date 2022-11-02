<template>
    <div id="service-inside-index">
        <loading-component />

        <header-block />

        <main id="main" class="site-main content-no-spacing">
            <div class="content">
                <div class="clearfix">
                    <page-title-block />

                    <div class="wrapper">
                        <video-block spacer-class="spacer p-top-xl" />
                    </div>

                    <how-it-works-block spacer-class="" />

                    <price-plans-block />

                    <clients-block spacer-class="m-top-xl" />
                </div>
            </div>
        </main>

        <footer-block />
    </div>
</template>

<script>
    import Loading from '../../components/Loading/Loading';
    import Header from '../../blocks/HeaderSecondary';
    import Footer from '../../blocks/Footer';

    import PageTitle from '../../blocks/service-inside/PageTitle';
    import Video from '../../blocks/index/Video';
    import HowItWorks from '../../blocks/index/HowItWorks';
    import PricePlans from '../../blocks/index/PricePlans';
    import Clients from '../../blocks/index/Clients';

    export default {
        components: {
            'loading-component': Loading,
            'header-block': Header,
            'footer-block': Footer,
            'page-title-block': PageTitle,
            'video-block': Video,
            'how-it-works-block': HowItWorks,
            'price-plans-block': PricePlans,
            'clients-block': Clients
        },
        mounted: function() {
            document.body.classList.add( 'page' );
            document.body.classList.add( 'title-opacity-true' );
        },
        metaInfo: {
            title: 'Service inside | Malex - Business Consulting Agency Vue JS Template',
            titleTemplate: '%s'
        }
    }
</script>
