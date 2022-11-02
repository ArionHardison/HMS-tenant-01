<template>
    <fragment>
        <footer id="footer" class="site-footer">
            <div class="wrapper">
                <back-to-top-component />

                <div class="footer">
                    <div class="d-flex flex-column flex-md-row flex-lg-row flex-xl-row justify-content-between">
                        <div class="align-self-center">
                            <div class="logo logo-secondary">
                                <img src="assets/img/logo/logo-light.svg" alt="Logo">
                            </div>
                        </div>

                        <div class="align-self-center">
                            <div class="copyright">
                                <p>© {{ new Date().getFullYear() }} Business Consulting Agency Vue JS Template By
                                    <a href="https://www.adveits.com">Adveits</a>
                                </p>
                            </div>
                        </div>

                        <div class="align-self-center">
                            <nav class="menu-secondary">
                                <ul class="nav">
                                    <li class="nav-item">
                                        <a title="LinkedIn" href="https://www.linkedin.com/company/18135051/"><i class="fab fa-linkedin-in"></i></a>
                                    </li>

                                    <li class="nav-item">
                                        <a title="Facebook" href="https://www.facebook.com/adveits/"><i class="fab fa-facebook-f"></i></a>
                                    </li>
                                </ul>
                            </nav>
                        </div>
                    </div>
                </div>
            </div>
        </footer>

        <div id="modals">
            <menu-modal-component logo-class="light" />
            <search-modal-component logo-class="light" />
            <plans-modal-component />
        </div>
    </fragment>
</template>

<script>
    import BackToTop from '../components/Button/BackToTop';
    import MenuModal from '../components/Modal/MenuModal';
    import SearchModal from '../components/Modal/SearchModal';
    import PlansModal from '../components/Modal/PlansModal';
    import { Fragment } from 'vue-fragment';

    export default {
        name: 'Footer',
        components: {
            Fragment,
            'back-to-top-component': BackToTop,
            'menu-modal-component': MenuModal,
            'search-modal-component': SearchModal,
            'plans-modal-component': PlansModal
        }
    }
</script>
