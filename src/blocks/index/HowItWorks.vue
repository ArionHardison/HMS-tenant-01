<template>
    <section id="how-it-works" :class="'block bg-white before-block spacer '+ spacerClass +''">
        <div class="wrapper">
            <div class="row no-gutters process-height">
                <div class="col-sm-12 col-md-3 col-lg-3 col-xl-3">
                    <div class="process pl-0">
                        <div class="process-content">
                            <h6 class="process-small-t-head">How it Works?</h6>
                            <div class="process-description">
                                <h2>We Guarantee a Stable Work Process</h2>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="col-sm-12 col-md-9 col-lg-9 col-xl-9">
                    <div class="row no-gutters h-100">
                        <div class="col-sm-12 col-md-4 col-lg-4 col-xl-4">
                            <div class="process process-color-1">
                                <div class="process-content">
                                    <h4 class="process-t-head">Business Analysis</h4>
                                    <p class="process-description">At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium.</p>
                                </div>

                                <div class="process-number">01</div>
                            </div>
                        </div>

                        <div class="col-sm-12 col-md-4 col-lg-4 col-xl-4">
                            <div class="process process-color-2">
                                <div class="process-content">
                                    <h4 class="process-t-head">Business Planning</h4>
                                    <p class="process-description">At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium.</p>
                                </div>

                                <div class="process-number">02</div>
                            </div>
                        </div>

                        <div class="col-sm-12 col-md-4 col-lg-4 col-xl-4">
                            <div class="process process-color-3">
                                <div class="process-content">
                                    <h4 class="process-t-head">Business Growth</h4>
                                    <p class="process-description">At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium.</p>
                                </div>

                                <div class="process-number">03</div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
    export default {
        name: 'HowItWorks',
        props: ['spacerClass']
    }
</script>
