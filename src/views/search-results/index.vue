<template>
    <div id="search-results-index">
        <header-block />

        <loading-component />

        <main id="main" class="site-main">
            <page-title-block />

            <div id="page-content" class="spacer p-top-xl">
                <div class="wrapper">
                    <div class="content">
                        <div class="row gutter-width-md with-pb-lg">
                            <div v-for="searchItem in searchItems" :key="searchItem.id" class="col-xl-4 col-lg-4 col-md-4 col-sm-12">
                                <div class="card card-post">
                                    <div class="card-body p-0">
                                        <h5 class="card-title">
                                            <router-link :title="searchItem.title" class="d-block" :to="searchItem.link">{{ searchItem.title }}</router-link>
                                        </h5>

                                        <p class="card-text">{{ searchItem.description }}</p>

                                        <div class="card-btn">
                                            <router-link title="Read more" class="btn btn-sm btn-link btn-icon-hover p-0 border-0 min-w-auto link-no-space text-uppercase" :to="searchItem.link">
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

    import PageTitle from '../../blocks/search-results/PageTitle';
    import SearchItems from '../../data/search-results/searchItems.json';
    import Loadmore from '../../components/Loadmore/Loadmore';

    export default {
        data() {
            return {
                searchItems: SearchItems.searchItems
            };
        },
        components: {
            'loading-component': Loading,
            'header-block': Header,
            'footer-block': Footer,
            'page-title-block': PageTitle,
            'loadmore-component': Loadmore
        },
        mounted: function() {
            document.body.classList.add( 'search-results' );
            document.body.classList.add( 'title-opacity-true' );
        },
        beforeDestroy() {
            document.body.classList.remove( 'search-results' );
            document.body.classList.remove( 'title-opacity-true' );
        },
        metaInfo: {
            title: 'Search results | Malex - Business Consulting Agency Vue JS Template',
            titleTemplate: '%s'
        }
    };
</script>
