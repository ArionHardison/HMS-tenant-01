<template>
    <button @click="togglePlansModal" class="btn btn-outline-secondary">Choose Plan</button>
</template>

<script>
    export default {
        name: 'PlansModalButton',
        props: ['orderText'],
        methods: {
            togglePlansModal: function( event ) {
                this.$store.commit( 'togglePlansModal', this.orderText )
            }
        }
    }
</script>
