<template>
    <div class="menu">
        <nav class="menu-primary">
            <ul class="nav">
                <li :class="[currentPage.includes('service-inside') ? activeClass : '', 'nav-item']">
                    <router-link title="Services" to="/#services">Services</router-link>
                </li>

                <li :class="[currentPage.includes('about-us') ? activeClass : '', 'nav-item']">
                    <router-link title="About Us" to="/#about-us">About Us</router-link>
                </li>

                <li class="nav-item">
                    <router-link title="Teams" to="/#team-members">Team</router-link>
                </li>

                <li class="nav-item">
                    <router-link title="Pricing" to="/#price-plans">Pricing</router-link>
                </li>

                <li class="nav-item">
                    <router-link title="Testimonials" to="/#testimonials">Testimonials</router-link>
                </li>

                <li :class="[currentPage.includes('news') ? activeClass : '', 'nav-item']">
                    <router-link title="News" to="/news">News</router-link>
                </li>

                <li class="nav-item">
                    <router-link title="Contacts" to="/#contacts">Contacts</router-link>
                </li>
            </ul>
        </nav>
    </div>
</template>

<script>
    export default {
        name: 'HeaderMenuSecondary',
        data() {
            return {
                activeClass: 'current-nav-item'
            }
        },
        computed: {
            currentPage() {
                return this.$route.path;
            }
        }
    }
</script>
