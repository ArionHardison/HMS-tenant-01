<template>
    <section id="page-title" class="block with-img with-service-items" style="background-image: url('assets/img/placeholder/1920x1000.jpg')">
        <div class="wrapper d-flex flex-column justify-content-center">
            <div class="page-title-body page-title-body-space-left">
                <div class="title">
                    <h1 class="large">Business <br>Consulting Agency</h1>
                </div>

                <div class="description spacer p-top-lg">
                    <p>We are digital business consulting agency that helps companies increase better incomes and help with branding for faster business growing.</p>
                </div>

                <div class="spacer p-top-lg">
                    <router-link to="/about-us" class="btn btn-outline-tertiary">Learn More</router-link>
                </div>
            </div>

            <div class="page-title-footer full-width">
                <div class="d-flex justify-content-between">
                    <a @click="scrollToSection('#services')" href="#services" class="scroll-to-id scroll-animation">
                        <i class="malex-icon-long-arrow-down i-large-2"></i>
                    </a>

                    <div class="align-self-end">
                        <nav class="languages">
                            <ul class="nav">
                                <li class="lang-item current-lang">
                                    <router-link title="En" to="/">En</router-link>
                                </li>

                                <li class="lang-item">
                                    <router-link title="Ru" to="/">Ru</router-link>
                                </li>
                            </ul>
                        </nav>
                    </div>
                </div>
            </div>
        </div>

        <div class="page-title-bg-color"></div>
    </section>
</template>

<script>
    export default {
        name: 'PageTitle'
    }
</script>
