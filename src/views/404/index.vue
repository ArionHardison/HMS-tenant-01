<template>
    <div id="404-index">
        <loading-component />

        <header-block />

        <main id="main" class="site-main">
            <page-title-block />

            <div id="page-content" class="spacer p-top-lg">
                <div class="wrapper">
                    <div class="content">
                        <p class="text after">The page you were looking for couldn't be found. The page could be removed or you misspelled the word while searching for it. Maybe try a search?</p>

                        <div class="form">
                            <search-form-component />
                        </div>

                        <div class="button">
                            <back-to-home-component />
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

    import PageTitle from '../../blocks/404/PageTitle';
    import SearchForm from '../../components/Forms/SearchForm';
    import BackToHome from '../../components/Button/BackToHome';

    export default {
        components: {
            'loading-component': Loading,
            'header-block': Header,
            'footer-block': Footer,
            'page-title-block': PageTitle,
            'search-form-component': SearchForm,
            'back-to-home-component': BackToHome
        },
        mounted: function() {
            document.body.classList.add( 'error404' );
            document.body.classList.add( 'title-opacity-true' );
        },
        beforeDestroy() {
            document.body.classList.remove( 'error404' );
            document.body.classList.remove( 'title-opacity-true' );
        },
        metaInfo: {
            title: '404 | Malex - Business Consulting Agency Vue JS Template',
            titleTemplate: '%s'
        }
    };
</script>
