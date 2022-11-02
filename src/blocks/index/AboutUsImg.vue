<template>
    <div id="img" :class="'block spacer '+ spacerClass +' wrapper-normal'">
        <div class="wrapper">
            <div class="img-size-1">
                <div class="img object-fit">
                    <div class="object-fit-cover">
                        <img src="assets/img/placeholder/1600x800.jpg" alt="Team">
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'AboutUsImg',
        props: ['spacerClass']
    }
</script>
