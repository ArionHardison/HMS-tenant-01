<template>
    <section id="team-members" :class="'block bg-white-before spacer '+ spacerClass +''">
        <div class="wrapper">
            <div class="title">
                <h6 class="text-primary text-uppercase">Meet our team</h6>
            </div>

            <div class="title-opacity">
                <div class="title-opacity-text">Team</div>
            </div>

            <div class="description">
                <h2>We are Business Consulting Professionals</h2>
            </div>

            <div class="row gutter-width-md with-pb-md spacer p-top-lg">
                <div class="col-sm-12 col-md-4 col-lg-4 col-xl-4">
                    <div class="team-member">
                        <div class="team-member-top">
                            <div class="img object-fit">
                                <div class="object-fit-cover">
                                    <img src="assets/img/placeholder/500x550.jpg" alt="Tom Henders">
                                </div>
                            </div>

                            <div class="team-member-position">
                                <p>CEO</p>
                            </div>
                        </div>

                        <div class="team-member-content">
                            <h4 class="team-member-t-head">Tom Henders</h4>

                            <div class="team-member-description">
                                <p>At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium.</p>
                            </div>
                        </div>

                        <nav class="team-member-nav-items">
                            <ul class="nav">
                                <li class="nav-item">
                                    <a title="Facebook" href="https://www.facebook.com/adveits/"><i class="fab fa-facebook-f"></i></a>
                                </li>

                                <li class="nav-item">
                                    <a title="LinkedIn" href="https://www.linkedin.com/company/18135051/"><i class="fab fa-linkedin-in"></i></a>
                                </li>

                                <li class="nav-item">
                                    <a title="Instagram" href="https://www.instagram.com/adveits/"><i class="fab fa-instagram"></i></a>
                                </li>
                            </ul>
                        </nav>
                    </div>
                </div>

                <div class="col-sm-12 col-md-4 col-lg-4 col-xl-4">
                    <div class="team-member">
                        <div class="team-member-top">
                            <div class="img object-fit">
                                <div class="object-fit-cover">
                                    <img src="assets/img/placeholder/500x550.jpg" alt="Andrew Mike">
                                </div>
                            </div>

                            <div class="team-member-position">
                                <p>Business Analytic</p>
                            </div>
                        </div>

                        <div class="team-member-content">
                            <h4 class="team-member-t-head">Andrew Mike</h4>

                            <div class="team-member-description">
                                <p>At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium.</p>
                            </div>
                        </div>

                        <nav class="team-member-nav-items">
                            <ul class="nav">
                                <li class="nav-item">
                                    <a title="Facebook" href="https://www.facebook.com/adveits/"><i class="fab fa-facebook-f"></i></a>
                                </li>

                                <li class="nav-item">
                                    <a title="LinkedIn" href="https://www.linkedin.com/company/18135051/"><i class="fab fa-linkedin-in"></i></a>
                                </li>

                                <li class="nav-item">
                                    <a title="Instagram" href="https://www.instagram.com/adveits/"><i class="fab fa-instagram"></i></a>
                                </li>
                            </ul>
                        </nav>
                    </div>
                </div>

                <div class="col-sm-12 col-md-4 col-lg-4 col-xl-4">
                    <div class="team-member">
                        <div class="team-member-top">
                            <div class="img object-fit">
                                <div class="object-fit-cover">
                                    <img src="assets/img/placeholder/500x550.jpg" alt="Rosie Ford">
                                </div>
                            </div>

                            <div class="team-member-position">
                                <p>Marketing Agent</p>
                            </div>
                        </div>

                        <div class="team-member-content">
                            <h4 class="team-member-t-head">Rosie Ford</h4>

                            <div class="team-member-description">
                                <p>At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium.</p>
                            </div>
                        </div>

                        <nav class="team-member-nav-items">
                            <ul class="nav">
                                <li class="nav-item">
                                    <a title="Facebook" href="https://www.facebook.com/adveits/"><i class="fab fa-facebook-f"></i></a>
                                </li>

                                <li class="nav-item">
                                    <a title="LinkedIn" href="https://www.linkedin.com/company/18135051/"><i class="fab fa-linkedin-in"></i></a>
                                </li>

                                <li class="nav-item">
                                    <a title="Instagram" href="https://www.instagram.com/adveits/"><i class="fab fa-instagram"></i></a>
                                </li>
                            </ul>
                        </nav>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
    export default {
        name: 'TeamMembers',
        props: ['spacerClass']
    }
</script>
