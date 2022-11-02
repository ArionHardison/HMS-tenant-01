<template>
    <div id="news-index">
        <loading-component />

        <header-block />

        <main id="main" class="site-main">
            <page-title-block />

            <div id="page-content" class="spacer p-top-xl">
                <div class="wrapper">
                    <div class="content">
                        <div id="blog">
                            <div class="row gutter-width-md">
                                <div class="col-xl-8 col-lg-8 col-md-8 col-sm-12">
                                    <div class="row gutter-width-md with-pb-lg">
                                        <div v-for="newsItem in newsItems" :key="newsItem.id" class="col-xl-6 col-lg-6 col-md-6 col-sm-12">
                                            <div class="card card-post">
                                                <div class="card-top position-relative">
                                                    <router-link :title="newsItem.title" :to="newsItem.link">
                                                        <div class="img object-fit overflow-hidden">
                                                            <div class="object-fit-cover transform-scale-h">
                                                                <img class="card-top-img" :src="newsItem.imgLink" :alt="newsItem.imgAlt">
                                                            </div>
                                                        </div>
                                                    </router-link>
                                                </div>

                                                <div class="card-body">
                                                    <h5 class="card-title">
                                                        <router-link :title="newsItem.title" :to="newsItem.link">{{ newsItem.title }}</router-link>
                                                    </h5>

                                                    <p class="card-text">{{ newsItem.description }}</p>

                                                    <div class="card-btn">
                                                        <router-link title="Read more" class="btn btn-sm btn-link btn-icon-hover p-0 border-0 min-w-auto link-no-space text-uppercase" :to="newsItem.link">
                                                            <i class="malex-icon-arrow-right i-large"></i>
                                                            <span class="btn-text">Read more</span>
                                                        </router-link>
                                                    </div>
                                                </div>
                                            </div>
                                        </div>
                                    </div>

                                    <loadmore-component />
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

    import PageTitle from '../../blocks/news/PageTitle';
    import NewsItems from '../../data/news/newsItems.json';
    import Loadmore from '../../components/Loadmore/Loadmore';
    import Sidebar from '../../blocks/news/Sidebar';

    export default {
        data() {
            return {
                newsItems: NewsItems.newsItems
            };
        },
        components: {
            'loading-component': Loading,
            'header-block': Header,
            'footer-block': Footer,
            'page-title-block': PageTitle,
            'loadmore-component': Loadmore,
            'sidebar-block': Sidebar
        },
        methods: {
            goBack() {
                this.$router.push( "/" );
            }
        },
        mounted: function() {
            document.body.classList.add( 'blog' );
            document.body.classList.add( 'title-opacity-true' );
        },
        beforeDestroy() {
            document.body.classList.remove( 'blog' );
            document.body.classList.remove( 'title-opacity-true' );
        },
        metaInfo: {
            title: 'Our News | Malex - Business Consulting Agency Vue JS Template',
            titleTemplate: '%s'
        }
    };
</script>

