<template>
    <section id="about-us" :class="'block spacer '+ spacerClass +''">
        <div class="wrapper">
            <div class="title">
                <h6 class="text-primary text-uppercase">About Us</h6>
            </div>

            <div class="row gutter-width-md with-pb-md">
                <div class="col-sm-12 col-md-6 col-lg-6 col-xl-6">
                    <div class="description-2">
                        <h2>Keep Your Business Safe & Ensure High Availability</h2>
                    </div>

                    <div class="signature spacer m-top-lg">
                        <div class="signature-img">
                            <img src="assets/img/demo/23_img.png" alt="Signature">
                        </div>

                        <div class="signature-content">
                            <h5 class="signature-name">Tom Henders</h5>
                            <p class="signature-position">CEO of Company</p>
                        </div>
                    </div>
                </div>

                <div class="col-sm-12 col-md-6 col-lg-6 col-xl-6">
                    <div class="description-2">
                        <p>A business consulting agency is involved in the planning, implementation, and education of businesses. We work directly with business owners on developing a business plan, identifying marketing needs and developing the necessary skills for business ownership.</p>
                    </div>

                    <div class="description-2 spacer p-top-lg">
                        <p>Marketing consultant is an advisor who works with companies to create and implement marketing strategies.</p>
                    </div>
                </div>
            </div>

            <div class="icon-list">
                <div class="icon-list-items">
                    <div class="icon-list-item">
                        <p>
                            <span class="d-flex"><i class="fas fa-check"></i><span>Constant Improvement</span></span>
                        </p>
                    </div>

                    <div class="icon-list-item">
                        <p>
                            <span class="d-flex"><i class="fas fa-check"></i><span>Commitment to Customers</span></span>
                        </p>
                    </div>

                    <div class="icon-list-item">
                        <p>
                            <span class="d-flex"><i class="fas fa-check"></i><span>Best Quality You Can Get</span></span>
                        </p>
                    </div>

                    <div class="icon-list-item">
                        <p>
                            <span class="d-flex"><i class="fas fa-check"></i><span>30 Days Money Back Warranty</span></span>
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
    export default {
        name: 'AboutUs',
        props: ['spacerClass']
    }
</script>
