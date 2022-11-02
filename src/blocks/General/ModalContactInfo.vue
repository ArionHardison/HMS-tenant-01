<template>
    <fragment>
        <p>575 Crescent Avenue <br>PA 18951 <br>United Kingdom</p>
        <p>
            <a href="tel:+43253312523">+432 533 12 523</a><br>
            <a href="mailto:info@domain.com">info@domain.com</a>
        </p>
    </fragment>
</template>

<script>
    import { Fragment } from 'vue-fragment';

    export default {
        name: 'ModalContactInfo',
        components: {
            Fragment
        }
    }
</script>
