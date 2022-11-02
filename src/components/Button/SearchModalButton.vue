<template>
    <div :class="'search-toggle ' + buttonClass">
        <button @click="toggleSearchModal" :class="'btn btn-lg ' + btnOutline + ' btn-round p-0 min-w-auto'">
            <i class="fas fa-search"></i>
        </button>
    </div>
</template>

<script>
    export default {
        name: 'SearchModalButton',
        props: ['buttonClass', 'btnOutline'],
        methods: {
            toggleSearchModal: function( event ) {
                this.$store.commit( 'toggleSearchModal' )
            }
        }
    }
</script>
