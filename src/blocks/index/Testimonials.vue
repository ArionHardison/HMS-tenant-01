<template>
    <section id="testimonials" class="block bg-dark spacer p-top-xl p-bottom-xl">
        <div class="wrapper">
            <div class="title">
                <h6 class="text-primary text-uppercase">Testimonials</h6>
            </div>

            <div class="description text-tertiary">
                <h2>Our Happy Customers Reviews</h2>
            </div>

            <div class="adv-slider-reviews text-tertiary">
                <div class="adv-slider-reviews-img">
                    <img src="assets/img/demo/11_img.png" alt="Icon">
                </div>

                <div class="adv-swiper-container reviews-text">
                    <div class="adv-swiper-wrapper reviews-text-items">
                        <div v-for="testimonialItem in testimonialItems" :key="testimonialItem.id" class="adv-swiper-slide reviews-text-item">
                            <div class="reviews-text-item-content">
                                <h3>{{ testimonialItem.reviewsText }}</h3>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="d-flex align-items-center thumbs">
                    <div class="adv-swiper-container reviews-thumbs">
                        <div class="adv-swiper-wrapper reviews-thumbs-items">
                            <div v-for="testimonialItem in testimonialItems" :key="testimonialItem.id" @click="thumbClick" class="adv-swiper-slide reviews-thumbs-item" :data-reviews-name="testimonialItem.reviewsName" :data-reviews-position="testimonialItem.reviewsPosition">
                                <img :src="testimonialItem.reviewsImageSource" :alt="testimonialItem.reviewsName">
                            </div>
                        </div>
                    </div>

                    <div class="reviews-results">
                        <h6 class="reviews-name" id="reviews-name">{{ this.reviewName }}</h6>
                        <p class="reviews-positions" id="reviews-positions">{{ this.reviewPositions }}</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
    import Swiper from 'swiper';
    import TestimonialItems from '../../data/index/testimonialItems.json';

    export default {
        name: 'Testimonials',
        data() {
            return {
                'reviewName': 'Tomy Anderson',
                'reviewPositions': 'CEO at Company',
                testimonialItems: TestimonialItems.testimonialItems
            }
        },
        methods: {
            thumbClick: function ( event ) {
                this.reviewName = event.currentTarget.getAttribute( 'data-reviews-name' );
                this.reviewPositions = event.currentTarget.getAttribute( 'data-reviews-position' );
            }
        },
        mounted() {
            var swiper_adv_reviews_thumbs = new Swiper( '.adv-slider-reviews .adv-swiper-container.reviews-thumbs', {
                // ADV swiper
                noSwipingClass: 'adv-swiper-no-swiping',
                containerModifierClass: 'adv-swiper-container-',
                slideClass: 'adv-swiper-slide',
                slideBlankClass: 'adv-swiper-slide-invisible-blank',
                slideActiveClass: 'adv-swiper-slide-active',
                slideDuplicateActiveClass: 'adv-swiper-slide-duplicate-active',
                slideVisibleClass: 'adv-swiper-slide-visible',
                slideDuplicateClass: 'adv-swiper-slide-duplicate',
                slideNextClass: 'adv-swiper-slide-next',
                slideDuplicateNextClass: 'adv-swiper-slide-duplicate-next',
                slidePrevClass: 'adv-swiper-slide-prev',
                slideDuplicatePrevClass: 'adv-swiper-slide-duplicate-prev',
                wrapperClass: 'adv-swiper-wrapper',
                slidesPerView: 3,
                spaceBetween: 0,
                loop: false,
                freeMode: false
            } );

            new Swiper( '.adv-slider-reviews .adv-swiper-container.reviews-text', {
                // ADV swiper
                noSwipingClass: 'adv-swiper-no-swiping',
                containerModifierClass: 'adv-swiper-container-',
                slideClass: 'adv-swiper-slide',
                slideBlankClass: 'adv-swiper-slide-invisible-blank',
                slideActiveClass: 'adv-swiper-slide-active',
                slideDuplicateActiveClass: 'adv-swiper-slide-duplicate-active',
                slideVisibleClass: 'adv-swiper-slide-visible',
                slideDuplicateClass: 'adv-swiper-slide-duplicate',
                slideNextClass: 'adv-swiper-slide-next',
                slideDuplicateNextClass: 'adv-swiper-slide-duplicate-next',
                slidePrevClass: 'adv-swiper-slide-prev',
                slideDuplicatePrevClass: 'adv-swiper-slide-duplicate-prev',
                wrapperClass: 'adv-swiper-wrapper',
                thumbs: {
                    slideThumbActiveClass: 'adv-swiper-slide-thumb-active',
                    thumbsContainerClass: 'adv-swiper-container-thumbs',
                    swiper: swiper_adv_reviews_thumbs
                },
                spaceBetween: 0,
                allowTouchMove: false
            } );
        }
    }
</script>
