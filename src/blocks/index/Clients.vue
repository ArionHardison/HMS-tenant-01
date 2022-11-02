<template>
    <div id="clients" :class="'block bg-white spacer '+ spacerClass +''">
        <div class="wrapper">
            <div class="clients">
                <div class="clients-items">
                    <div class="clients-item">
                        <div class="clients-item-content">
                            <img src="assets/img/demo/06_img.png" alt="Balkan">
                        </div>
                    </div>

                    <div class="clients-item">
                        <div class="clients-item-content">
                            <img src="assets/img/demo/07_img.png" alt="Adveits">
                        </div>
                    </div>

                    <div class="clients-item">
                        <div class="clients-item-content">
                            <img src="assets/img/demo/08_img.png" alt="Swiger">
                        </div>
                    </div>

                    <div class="clients-item">
                        <div class="clients-item-content">
                            <img src="assets/img/demo/09_img.png" alt="The mandala community">
                        </div>
                    </div>

                    <div class="clients-item">
                        <div class="clients-item-content">
                            <img src="assets/img/demo/06_img.png" alt="Balkan">
                        </div>
                    </div>

                    <div class="clients-item">
                        <div class="clients-item-content">
                            <img src="assets/img/demo/07_img.png" alt="Adveits">
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Clients',
        props: ['spacerClass']
    }
</script>
