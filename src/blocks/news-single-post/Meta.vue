<template>
    <div class="meta">
        <p>
            <span><router-link to="/news">By admin</router-link></span>
            <span>-</span>
            <span>Comments (1)</span>
            <span>-</span>
            <span class="category"><router-link title="Business" to="/news">Business</router-link></span>
        </p>
    </div>
</template>

<script>
    export default {
        name: 'Meta'
    }
</script>
