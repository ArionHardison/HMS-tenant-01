<template>
    <div :class="'menu-toggle '+ buttonClass">
        <button @click="toggleMenuModal" :class="'btn btn-lg '+ btnOutline +' btn-round p-0 min-w-auto '">
            <i class="fas fa-bars"></i>
        </button>
    </div>
</template>

<script>
    export default {
        name: 'MenuModalButton',
        props: ['buttonClass', 'btnOutline'],
        methods: {
            toggleMenuModal: function( event ) {
                this.$store.commit( 'toggleMenuModal' )
            }
        }
    }
</script>
