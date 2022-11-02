<template>
    <div id="video" :class="'block '+ spacerClass +''">
        <FsLightbox :toggler="toggler" :sources="['https://www.youtube.com/watch?v=lSNmfy_KOJg']" />

        <div class="embed">
            <div class="embed-image-overlay">
                <button class="embed-click" @click="toggler = !toggler">
                    <div class="embed-center">
                        <div class="embed-play">
                            <i class="fas fa-play"></i>
                        </div>
                    </div>
                </button>

                <div class="embed-image">
                    <div class="img object-fit">
                        <div class="object-fit-cover">
                            <img src="assets/img/placeholder/1920x800.jpg" alt="Video">
                        </div>
                    </div>
                </div>

                <div class="embed-bg"></div>
            </div>
        </div>
    </div>
</template>

<script>
    import FsLightbox from 'fslightbox-vue';

    export default {
        name: 'Video',
        props: ['spacerClass'],
        components: { FsLightbox },
        data() {
            return {
                toggler: false
            }
        }
    }
</script>
