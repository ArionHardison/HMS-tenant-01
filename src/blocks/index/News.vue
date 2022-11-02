<template>
    <section id="news" class="block spacer p-top-xl-2 m-top-xl-2 p-bottom-xl">
        <div class="wrapper">
            <div class="title">
                <h6 class="text-primary text-uppercase">New Articles</h6>
            </div>

            <div class="title-opacity">
                <div class="title-opacity-text">News</div>
            </div>

            <div class="description">
                <h2>Check Our Latest Blog Posts</h2>
            </div>

            <div class="blog-shortcode">
                <div class="row gutter-width-md with-pb-md spacer p-top-lg">
                    <div class="col-xl-4 col-lg-4 col-md-4 col-sm-12">
                        <div class="card card-post">
                            <div class="card-top position-relative">
                                <router-link title="5 Tips for Sustainable Business Success" to="/news-single-post">
                                    <div class="img object-fit overflow-hidden">
                                        <div class="object-fit-cover transform-scale-h">
                                            <img class="card-top-img" src="assets/img/placeholder/500x334.jpg" alt="5 Tips for Sustainable Business Success">
                                        </div>
                                    </div>
                                </router-link>
                            </div>

                            <div class="card-body">
                                <h5 class="card-title">
                                    <router-link title="5 Tips for Sustainable Business Success" to="/news-single-post">5 Tips for Sustainable Business Success</router-link>
                                </h5>

                                <p class="card-text">At vero eos et accusamus et iusto odio dignissimos ducims…</p>

                                <div class="card-btn">
                                    <router-link title="Read more" class="btn btn-sm btn-link btn-icon-hover p-0 border-0 min-w-auto link-no-space text-uppercase" to="/news-single-post">
                                        <i class="malex-icon-arrow-right i-large"></i>
                                        <span class="btn-text">Read more</span>
                                    </router-link>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="col-xl-4 col-lg-4 col-md-4 col-sm-12">
                        <div class="card card-post">
                            <div class="card-top position-relative">
                                <router-link title="Assessing the Maturity of Your Data Management in Industry" to="/news-single-post">
                                    <div class="img object-fit overflow-hidden">
                                        <div class="object-fit-cover transform-scale-h">
                                            <img class="card-top-img" src="assets/img/placeholder/500x334.jpg" alt="Assessing the Maturity of Your Data Management in Industry">
                                        </div>
                                    </div>
                                </router-link>
                            </div>

                            <div class="card-body">
                                <h5 class="card-title">
                                    <router-link title="Assessing the Maturity of Your Data Management in Industry" to="/news-single-post">Assessing the Maturity of Your Data Management in Industry</router-link>
                                </h5>

                                <p class="card-text">At vero eos et accusamus et iusto odio dignissimos ducims…</p>

                                <div class="card-btn">
                                    <router-link title="Read more" class="btn btn-sm btn-link btn-icon-hover p-0 border-0 min-w-auto link-no-space text-uppercase" to="/news-single-post">
                                        <i class="malex-icon-arrow-right i-large"></i>
                                        <span class="btn-text">Read more</span>
                                    </router-link>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="col-xl-4 col-lg-4 col-md-4 col-sm-12">
                        <div class="card card-post">
                            <div class="card-top position-relative">
                                <router-link title="How to Build Your Sustainable Susiness Strategy" to="/news-single-post">
                                    <div class="img object-fit overflow-hidden">
                                        <div class="object-fit-cover transform-scale-h">
                                            <img class="card-top-img" src="assets/img/placeholder/500x334.jpg" alt="How to Build Your Sustainable Susiness Strategy">
                                        </div>
                                    </div>
                                </router-link>
                            </div>

                            <div class="card-body">
                                <h5 class="card-title">
                                    <router-link title="How to Build Your Sustainable Susiness Strategy" to="/news-single-post">How to Build Your Sustainable Susiness Strategy</router-link>
                                </h5>

                                <p class="card-text">At vero eos et accusamus et iusto odio dignissimos ducims…</p>

                                <div class="card-btn">
                                    <router-link title="Read more" class="btn btn-sm btn-link btn-icon-hover p-0 border-0 min-w-auto link-no-space text-uppercase" to="/news-single-post">
                                        <i class="malex-icon-arrow-right i-large"></i>
                                        <span class="btn-text">Read more</span>
                                    </router-link>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="spacer m-top-lg text-right">
                <router-link title="View all news" class="btn btn-outline-secondary" to="/news">View All Posts</router-link>
            </div>
        </div>
    </section>
</template>

<script>
    export default {
        name: 'News'
    }
</script>
