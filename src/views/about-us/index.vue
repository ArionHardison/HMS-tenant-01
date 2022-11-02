<template>
    <div id="about-us-index">
        <loading-component />

        <header-block />

        <main id="main" class="site-main content-no-spacing">
            <div class="content">
                <div class="clearfix">
                    <page-title-block />

                    <about-us-img spacer-class="p-top-xl" />

                    <about-us-block spacer-class="p-top-xl p-bottom-xl" />

                    <team-members-block spacer-class="p-top-xl p-bottom-xl" />

                    <testimonials-block />

                    <clients-block spacer-class="" />
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

    import PageTitle from '../../blocks/about-us/PageTitle';
    import AboutUsImg from '../../blocks/index/AboutUsImg';
    import AboutUs from '../../blocks/index/AboutUs';
    import TeamMembers from '../../blocks/index/TeamMembers';
    import Testimonials from '../../blocks/index/Testimonials';
    import Clients from '../../blocks/index/Clients';

    export default {
        components: {
            'loading-component': Loading,
            'header-block': Header,
            'footer-block': Footer,
            'page-title-block': PageTitle,
            'about-us-img': AboutUsImg,
            'about-us-block': AboutUs,
            'team-members-block': TeamMembers,
            'testimonials-block': Testimonials,
            'clients-block': Clients
        },
        mounted: function() {
            document.body.classList.add( 'page' );
            document.body.classList.add( 'title-opacity-true' );
        },
        metaInfo: {
            title: 'About Us | Malex - Business Consulting Agency Vue JS Template',
            titleTemplate: '%s'
        }
    }
</script>
