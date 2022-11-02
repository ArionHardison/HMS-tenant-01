<template>
    <div class="header-logo">
        <router-link class="logo logo-primary adv-dark transform-scale-h" title="Logo" to="/">
            <img src="assets/img/logo/logo-dark.svg" alt="Logo">
        </router-link>

        <router-link class="logo logo-secondary adv-light transform-scale-h" title="Logo" to="/">
            <img src="assets/img/logo/logo-light.svg" alt="Logo">
        </router-link>
    </div>
</template>

<script>
    export default {
        name: 'LogoHeader'
    }
</script>
