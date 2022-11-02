<template>
    <div id="comments" class="comments-area spacer m-top-xl">
        <div class="comment-title">
            <h3>1 Comment</h3>
        </div>

        <ul class="comment-list list-unstyled style-default">
            <li class="comment">
                <div class="comment-wrapper">
                    <div class="comment-details">
                        <div class="comment-content">
                            <div class="comment-content-left">
                                <div class="comment-img">
                                    <img src="assets/img/placeholder/110x110.jpg" alt="Rosie Ford">
                                </div>
                            </div>

                            <div class="comment-content-right">
                                <h5 class="comment-author after">
                                    <router-link title="Rosie Ford" to="/news-single-post">Rosie Ford</router-link>
                                </h5>

                                <div class="comment-time">
                                    <p>29 February, 2020 3:23 pm</p>
                                </div>

                                <div class="comment-description">
                                    <p>No one rejects, dislikes, or avoids pleasure itself, because it is pleasure, but because those who do not know how to pursue pleasure rationally.</p>
                                </div>

                                <div class="comment-reply">
                                    <a @click="scrollToSection('#reply-title')" title="Reply" class="btn btn-sm btn-link btn-icon p-0 border-0 min-w-auto link-no-space text-uppercase scroll-to-id" href="#reply-title">
                                        <i class="malex-icon-arrow-right i-large"></i>
                                        <span class="btn-text">Reply</span>
                                    </a>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </li>
        </ul>

        <div class="block spacer m-top-xl">
            <div id="respond" class="comment-respond">
                <h3 id="reply-title" class="comment-reply-title">Leave a Reply
                    <router-link rel="nofollow" id="cancel-comment-reply-link" class="btn btn-link border-0 p-0 min-w-auto link-no-space" to="/news-single-post" style="display:none">Cancel Reply</router-link>
                </h3>

                <comment-form-component />
            </div>
        </div>
    </div>
</template>

<script>
    import CommentForm from '../../components/Forms/CommentForm';

    export default {
        name: 'Comments',
        components: {
            'comment-form-component': CommentForm
        }
    }
</script>
