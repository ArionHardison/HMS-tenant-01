<template>
    <section id="contacts" class="block bg-white-before spacer p-top-xl-2">
        <div id="contacts-0" class="wrapper spacer p-top-xl-2">
            <div class="title">
                <h6 class="text-primary text-uppercase">Contacts</h6>
            </div>

            <div class="title-opacity">
                <div class="title-opacity-text">Contacts</div>
            </div>

            <div class="description-lg">
                <h2>Any Questions? Contact us Freely and We'll Get Back to You Shortly</h2>
            </div>

            <div class="spacer p-top-lg">
                <div class="row gutter-width-md with-pb-md">
                    <div class="col-sm-12 col-md-4 col-lg-4 col-xl-4">
                        <div class="contacts-item">
                            <div class="contacts-item-icon">
                                <i class="malex-icon-location"></i>
                            </div>

                            <h5 class="contacts-item-t-head">Location</h5>

                            <p class="contacts-item-description">Location: 575 Crescent Avenue<br>Quakertown, PA 18951</p>
                        </div>
                    </div>

                    <div class="col-sm-12 col-md-4 col-lg-4 col-xl-4">
                        <div class="contacts-item">
                            <div class="contacts-item-icon">
                                <i class="malex-icon-phone"></i>
                            </div>

                            <h5 class="contacts-item-t-head">Phone no.</h5>

                            <p class="contacts-item-description">
                                Mobile:
                                <a href="tel:+43253312523">+432 533 12 523</a><br>
                                Fax:
                                <a href="tel:+53222212523">+532 222 12 523</a>
                            </p>
                        </div>
                    </div>

                    <div class="col-sm-12 col-md-4 col-lg-4 col-xl-4">
                        <div class="contacts-item">
                            <div class="contacts-item-icon">
                                <i class="malex-icon-email"></i>
                            </div>

                            <h5 class="contacts-item-t-head">E-mail</h5>

                            <p class="contacts-item-description">
                                Info:
                                <a href="mailto:info@domain.com">info@domain.com</a><br>
                                CEO:
                                <a href="mailto:ceo@domain.com">ceo@domain.com</a>
                            </p>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <div class="width-img spacer p-top-xl p-bottom-xl" style="background-image: url('assets/img/demo/18_img.png')">
            <div class="wrapper">
                <div id="contact-form">
                    <div class="title">
                        <h3 class="pb-0">You Can Write Us</h3>
                    </div>

                    <div class="description-lg spacer p-top-lg">
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. When an unknown printer took a galley.</p>
                    </div>

                    <div class="spacer p-top-lg">
                        <contacts-form-component />
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
    import ContactsForm from '../../components/Forms/ContactsForm';

    export default {
        name: 'Contacts',
        components: {
            'contacts-form-component': ContactsForm
        }
    }
</script>
