<template>
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
</template>

<script>
    export default {
        name: 'Languages'
    }
</script>
