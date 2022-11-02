<template>
    <div id="ui-index">
        <loading-component />

        <header-block />

        <main id="main" class="site-main">
            <div id="page-title">
                <div class="wrapper">
                    <div class="title">
                        <h1 class="large">Malex user interface (UI)</h1>
                    </div>

                    <div class="title-opacity">
                        <div class="title-opacity-text">UI</div>
                    </div>
                </div>
            </div>

            <div id="page-content" class="spacer p-top-xl">
                <div class="wrapper">
                    <div class="content">
                        <div class="row gutter-width-md">
                            <div class="col-xl-8 col-lg-8 col-md-8 col-sm-12">
                                <p>Malex project is created using Bootstrap 4 Framework and all of the examples below are based on it. Also, Malex includes custom classes, plugins and scripts which are also based on our experience of Bootstrap 4 Framework.</p>

                                <content-block />

                                <components-block />

                                <utilities-block />
                            </div>

                            <div class="col-xl-4 col-lg-4 col-md-4 col-sm-12" id="aside-sticky">
                                <sidebar-block />
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
    import Header from '../../blocks/ui/Header';
    import Footer from '../../blocks/ui/Footer';

    import Content from '../../blocks/ui/Content';
    import Components from '../../blocks/ui/Components';
    import Utilities from '../../blocks/ui/Utilities';
    import Sidebar from '../../blocks/ui/Sidebar';

    import Prism from 'vue-prismjs';
    import 'prismjs/themes/prism.css';

    export default {
        components: {
            'loading-component': Loading,
            'header-block': Header,
            'footer-block': Footer,
            'content-block': Content,
            'components-block': Components,
            'utilities-block': Utilities,
            'sidebar-block': Sidebar,
            Prism
        },
        mounted: function() {
            document.body.classList.add( 'page' );
            document.body.classList.add( 'ui' );
            document.body.classList.add( 'title-opacity-true' );
        },
        beforeDestroy() {
            document.body.classList.remove( '"page' );
            document.body.classList.remove( 'ui' );
            document.body.classList.remove( 'title-opacity-true' );
        },
        metaInfo: {
            title: 'UI | Malex - Business Consulting Agency Vue JS Template',
            titleTemplate: '%s'
        }
    }
</script>
