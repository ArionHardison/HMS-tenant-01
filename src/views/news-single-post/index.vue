<template>
    <div id="news-single-page-index">
        <header-block />

        <loading-component />

        <main id="main" class="site-main">
            <page-title-block />

            <div id="page-content" class="spacer p-top-xl">
                <div class="wrapper">
                    <div class="content">
                        <div id="single">
                            <div class="row gutter-width-md">
                                <div class="col-xl-8 col-lg-8 col-md-8 col-sm-12 single-content">
                                    <div class="img object-fit">
                                        <div class="object-fit-cover">
                                            <img src="assets/img/placeholder/1050x600.jpg" alt="Assessing the Maturity of Your Data Management in Industry">
                                        </div>
                                    </div>

                                    <meta-block />

                                    <title-block />

                                    <description-block />

                                    <tags-block />

                                    <comments-block />
                                </div>

                                <div class="col-xl-4 col-lg-4 col-md-4 col-sm-12">
                                    <sidebar-block />
                                </div>
                            </div>
                        </div>
                    </div>
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

    import PageTitle from '../../blocks/news-single-post/PageTitle';
    import Meta from '../../blocks/news-single-post/Meta';
    import Title from '../../blocks/news-single-post/Title';
    import Description from '../../blocks/news-single-post/Description';
    import Tags from '../../blocks/news-single-post/Tags';
    import Comments from '../../blocks/news-single-post/Comments';
    import Sidebar from '../../blocks/news/Sidebar';

    export default {
        components: {
            'loading-component': Loading,
            'header-block': Header,
            'footer-block': Footer,
            'page-title-block': PageTitle,
            'meta-block': Meta,
            'title-block': Title,
            'description-block': Description,
            'tags-block': Tags,
            'comments-block': Comments,
            'sidebar-block': Sidebar
        },
        mounted: function() {
            document.body.classList.add( 'single-post' );
            document.body.classList.add( 'title-opacity-true' );
        },
        beforeDestroy() {
            document.body.classList.remove( 'single-post' );
            document.body.classList.remove( 'title-opacity-true' );
        },
        metaInfo: {
            title: 'News single post | Malex - Business Consulting Agency Vue JS Template',
            titleTemplate: '%s'
        }
    };
</script>

