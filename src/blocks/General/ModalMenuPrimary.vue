<template>
    <nav class="menu-primary">
        <ul class="nav">
            <li :class="[currentPage.includes('service-inside') ? activeClass : '', 'nav-item']">
                <a v-if="currentPage === '/'" @click="handleClick('#services')" title="Services" href="#services">Services</a>
                <router-link v-else @click="toggleMenuModal" title="Services" to="/#services">Services</router-link>
            </li>

            <li :class="[currentPage.includes('about-us') ? activeClass : '', 'nav-item']">
                <a v-if="currentPage === '/'" @click="handleClick('#about-us')" title="About Us" href="#about-us">About Us</a>
                <router-link v-else @click="toggleMenuModal" title="About Us" to="/#about-us">About Us</router-link>
            </li>

            <li class="nav-item">
                <a v-if="currentPage === '/'" @click="handleClick('#team-members')" title="Team" href="#team-members">Team</a>
                <router-link v-else @click="toggleMenuModal" title="Team" to="/#team-members">Team</router-link>
            </li>

            <li class="nav-item">
                <a v-if="currentPage === '/'" @click="handleClick('#price-plan')" title="Pricing" href="#price-plan">Pricing</a>
                <router-link v-else @click="toggleMenuModal" title="Pricing" to="/#price-plans">Pricing</router-link>
            </li>

            <li class="nav-item">
                <a v-if="currentPage === '/'" @click="handleClick('#testimonials')" title="Testimonials" href="#testimonials">Testimonials</a>
                <router-link v-else @click="toggleMenuModal" title="Testimonials" to="/#testimonials">Testimonials</router-link>
            </li>

            <li :class="[currentPage.includes('news') ? activeClass : '', 'nav-item']">
                <a v-if="currentPage === '/'" @click="handleClick('#news')" title="News" href="#news">News</a>
                <router-link v-else @click="toggleMenuModal" title="News" to="/news">News</router-link>
            </li>

            <li class="nav-item">
                <a v-if="currentPage === '/'" @click="handleClick('#contacts')" title="Contacts" href="#contacts">Contacts</a>
                <router-link v-else @click="toggleMenuModal" title="Contacts" to="/#contacts">Contacts</router-link>
            </li>
        </ul>
    </nav>
</template>

<script>
    export default {
        name: 'ModalMenuPrimary',
        data() {
            return {
                activeClass: 'current-nav-item'
            }
        },
        methods: {
            handleClick: function ( id ) {
                this.toggleMenuModal();
                this.scrollToSection( id );
            },
            toggleMenuModal: function() {
                this.$store.commit( 'toggleMenuModal' );
                this.$store.commit( 'variablesNull' );
            }
        },
        computed: {
            currentPage() {
                return this.$route.path;
            }
        }
    }
</script>
