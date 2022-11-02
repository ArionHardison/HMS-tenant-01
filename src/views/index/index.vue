<template>
    <div id="home-index">
        <header-block logo-color="light" />

        <loading-component />

        <main id="main" class="site-main content-no-spacing">
            <div class="content">
                <div class="clearfix">
                    <page-title-block />

                    <services-block />

                    <about-us-block spacer-class="p-top-xl-2" />

                    <about-us-img spacer-class="p-top-lg" />

                    <how-it-works-block spacer-class="p-bottom-xl-2" />

                    <team-members-block spacer-class="p-top-xl-2 p-bottom-xl" />

                    <price-plans-block />

                    <clients-block spacer-class="m-top-xl" />

                    <video-block />

                    <testimonials-block />

                    <news-block />

                    <contacts-block />
                </div>
            </div>
        </main>

        <footer-block />
    </div>
</template>

<script>
    import Loading from '../../components/Loading/Loading';
    import Header from '../../blocks/HeaderPrimary';
    import Footer from '../../blocks/Footer';

    import PageTitle from '../../blocks/index/PageTitle';
    import Services from '../../blocks/index/Services';
    import AboutUs from '../../blocks/index/AboutUs';
    import AboutUsImg from '../../blocks/index/AboutUsImg';
    import HowItWorks from '../../blocks/index/HowItWorks';
    import TeamMembers from '../../blocks/index/TeamMembers';
    import PricePlans from '../../blocks/index/PricePlans';
    import Clients from '../../blocks/index/Clients';
    import Video from '../../blocks/index/Video';
    import Testimonials from '../../blocks/index/Testimonials';
    import News from '../../blocks/index/News';
    import Contacts from '../../blocks/index/Contacts';

    export default {
        components: {
            'header-block': Header,
            'loading-component': Loading,
            'page-title-block': PageTitle,
            'services-block': Services,
            'about-us-block': AboutUs,
            'about-us-img': AboutUsImg,
            'how-it-works-block': HowItWorks,
            'team-members-block': TeamMembers,
            'price-plans-block': PricePlans,
            'clients-block': Clients,
            'video-block': Video,
            'testimonials-block': Testimonials,
            'news-block': News,
            'contacts-block': Contacts,
            'footer-block': Footer
        },
        mounted: function() {
            document.body.classList.add( 'home' );
            document.body.classList.add( 'header-absolute-true' );
            document.body.classList.add( 'header-fixed-true' );
        },
        beforeDestroy() {
            document.body.classList.remove( 'home' );
            document.body.classList.remove( 'header-absolute-true' );
            document.body.classList.remove( 'header-fixed-true' );
            document.body.classList.remove( 'header-fixed' );
        },
        metaInfo: {
            title: 'Home | Malex - Business Consulting Agency Vue JS Template',
            titleTemplate: '%s'
        }
    };
</script>
