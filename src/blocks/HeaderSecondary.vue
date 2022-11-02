<template>
    <header id="header" class="site-header">
        <div class="wrapper">
            <div class="header-content d-flex justify-content-between">
                <div class="header-left align-self-center">
                    <logo-block logo-color="dark" />
                </div>

                <div class="header-right d-flex justify-content-end">
                    <div class="d-flex align-items-center">
                        <header-menu-secondary />

                        <search-modal-button-component btn-outline="btn-outline-secondary" />

                        <menu-modal-button-component btn-outline="btn-outline-secondary" />
                    </div>
                </div>
            </div>
        </div>
    </header>
</template>

<script>
    import Logo from './Logo';
    import HeaderMenu from './General/HeaderMenuSecondary';
    import MenuModalButton from '../components/Button/MenuModalButton';
    import SearchModalButton from '../components/Button/SearchModalButton';

    export default {
        name: 'Header404',
        components: {
            'search-modal-button-component': SearchModalButton,
            'menu-modal-button-component': MenuModalButton,
            'header-menu-secondary': HeaderMenu,
            'logo-block': Logo
        }
    }
</script>
