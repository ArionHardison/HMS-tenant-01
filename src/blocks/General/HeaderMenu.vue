<template>
    <div class="menu">
        <nav class="menu-primary">
            <ul class="nav">
                <li class="nav-item">
                    <a @click="scrollToSection('#services')" id="nav-services" title="Services" href="#services">Services</a>
                </li>

                <li class="nav-item">
                    <a @click="scrollToSection('#about-us')" id="nav-about-us" title="About Us" href="#about-us">About Us</a>
                </li>

                <li class="nav-item">
                    <a @click="scrollToSection('#team-members')" id="nav-team-members" title="Teams" href="#team-members">Team</a>
                </li>

                <li class="nav-item">
                    <a @click="scrollToSection('#price-plans')" id="nav-price-plans" title="Pricing" href="#price-plans">Pricing</a>
                </li>

                <li class="nav-item">
                    <a @click="scrollToSection('#testimonials')" id="nav-testimonials" title="Testimonials" href="#testimonials">Testimonials</a>
                </li>

                <li class="nav-item">
                    <a @click="scrollToSection('#news')" id="nav-news" title="News" href="#news">News</a>
                </li>

                <li class="nav-item">
                    <a @click="scrollToSection('#contacts')" id="nav-contacts" title="Contacts" href="#contacts">Contacts</a>
                </li>
            </ul>
        </nav>
    </div>
</template>

<script>
    export default {
        name: 'HeaderMenu'
    }
</script>
