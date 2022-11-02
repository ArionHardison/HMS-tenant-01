<template>
    <section id="price-plans" class="block spacer p-top-xl-2 m-top-xl-2">
        <div class="wrapper">
            <div class="title">
                <h6 class="text-primary text-uppercase">Price Plans</h6>
            </div>

            <div class="title-opacity">
                <div class="title-opacity-text">Plans</div>
            </div>

            <div class="description">
                <h2>Choose the Best Plan for You</h2>
            </div>

            <div class="row gutter-width-md with-pb-md spacer p-top-lg">
                <div class="col-sm-12 col-md-4 col-lg-4 col-xl-4">
                    <div class="price-table">
                        <div class="price-table-header">
                            <h4 class="price-table-t-head">Basic Plan</h4>
                            <p class="price-table-description">This is Basic Plan</p>
                        </div>

                        <div class="price-table-price">
                            <p>
                                <span class="currency">$</span><span class="price">79</span><span class="period">/ Monthly</span>
                            </p>
                        </div>

                        <ul class="price-table-list-group list-group">
                            <li class="list-group-item d-flex justify-content-between align-items-center">
                                Branding
                                <i class="text-primary fas fa-check i-small"></i>
                            </li>

                            <li class="list-group-item d-flex justify-content-between align-items-center">
                                20 hours of consultation
                                <i class="text-primary fas fa-check i-small"></i>
                            </li>

                            <li class="list-group-item d-flex justify-content-between align-items-center">
                                15 hours if theory
                                <i class="text-primary fas fa-check i-small"></i>
                            </li>

                            <li class="list-group-item d-flex justify-content-between align-items-center">
                                Skype video call
                                <i class="text-primary fas fa-check i-small"></i>
                            </li>

                            <li class="list-group-item d-flex justify-content-between align-items-center">
                                Support 24/7
                                <i class="text-primary fas fa-check i-small"></i>
                            </li>
                        </ul>

                        <div class="price-table-footer">
                            <PlansModalButton order-text="Basic plan" />
                        </div>
                    </div>
                </div>

                <div class="col-sm-12 col-md-4 col-lg-4 col-xl-4">
                    <div class="price-table">
                        <div class="price-table-header">
                            <h4 class="price-table-t-head">Standart Plan</h4>
                            <p class="price-table-description">This is Standart Plan</p>
                        </div>

                        <div class="price-table-price">
                            <p>
                                <span class="currency">$</span><span class="price">129</span><span class="period">/ Monthly</span>
                            </p>
                        </div>

                        <ul class="price-table-list-group list-group">
                            <li class="list-group-item d-flex justify-content-between align-items-center">
                                Branding
                                <i class="text-primary fas fa-check i-small"></i>
                            </li>

                            <li class="list-group-item d-flex justify-content-between align-items-center">
                                20 hours of consultation
                                <i class="text-primary fas fa-check i-small"></i>
                            </li>

                            <li class="list-group-item d-flex justify-content-between align-items-center">
                                15 hours if theory
                                <i class="text-primary fas fa-check i-small"></i>
                            </li>

                            <li class="list-group-item d-flex justify-content-between align-items-center">
                                Skype video call
                                <i class="text-primary fas fa-check i-small"></i>
                            </li>

                            <li class="list-group-item d-flex justify-content-between align-items-center">
                                Support 24/7
                                <i class="text-primary fas fa-check i-small"></i>
                            </li>
                        </ul>

                        <div class="price-table-footer">
                            <PlansModalButton order-text="Standart plan" />
                        </div>
                    </div>
                </div>

                <div class="col-sm-12 col-md-4 col-lg-4 col-xl-4">
                    <div class="price-table">
                        <div class="price-table-badge">
                            <p>Popular</p>
                        </div>

                        <div class="price-table-header">
                            <h4 class="price-table-t-head">Premium Plan</h4>
                            <p class="price-table-description">This is Premium Plan</p>
                        </div>

                        <div class="price-table-price">
                            <p>
                                <span class="currency">$</span><span class="price">259</span><span class="period">/ Monthly</span>
                            </p>
                        </div>

                        <ul class="price-table-list-group list-group">
                            <li class="list-group-item d-flex justify-content-between align-items-center">
                                Branding
                                <i class="text-primary fas fa-check i-small"></i>
                            </li>

                            <li class="list-group-item d-flex justify-content-between align-items-center">
                                20 hours of consultation
                                <i class="text-primary fas fa-check i-small"></i>
                            </li>

                            <li class="list-group-item d-flex justify-content-between align-items-center">
                                15 hours if theory
                                <i class="text-primary fas fa-check i-small"></i>
                            </li>

                            <li class="list-group-item d-flex justify-content-between align-items-center">
                                Skype video call
                                <i class="text-primary fas fa-check i-small"></i>
                            </li>

                            <li class="list-group-item d-flex justify-content-between align-items-center">
                                Support 24/7
                                <i class="text-primary fas fa-check i-small"></i>
                            </li>
                        </ul>

                        <div class="price-table-footer">
                            <PlansModalButton order-text="Premium plan" />
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
    import PlansModalButton from '../../components/Button/PlansModalButton';

    export default {
        name: 'PricePlans',
        components: {
            PlansModalButton,
        }
    }
</script>
