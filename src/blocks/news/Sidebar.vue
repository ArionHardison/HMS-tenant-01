<template>
    <aside id="aside" class="widget-area">
        <div class="widget widget_search">
            <form class="search-form" role="search" method="get" :action="urlAction">
                <div class="search input-group">
                    <input class="form-control form-control-lg" type="text" placeholder="Search" name="s">

                    <div class="input-group-append">
                        <button type="submit" class="btn btn-link border-0 p-0 min-w-auto">
                            <i class="fas fa-search"></i>
                        </button>
                    </div>
                </div>
            </form>
        </div>

        <div class="widget widget_categories">
            <h6 class="widget-title">Categories</h6>

            <ul>
                <li class="cat-item">
                    <router-link title="Strategy" to="/news">Strategy</router-link>
                </li>

                <li class="cat-item">
                    <router-link title="Sales" to="/news">Sales</router-link>
                </li>

                <li class="cat-item">
                    <router-link title="Marketing" to="/news">Marketing</router-link>
                </li>

                <li class="cat-item">
                    <router-link title="Business" to="/news">Business</router-link>
                </li>
            </ul>
        </div>

        <div class="widget widget_recent_entries">
            <h6 class="widget-title">Recent posts</h6>

            <ul class="list-unstyled items">
                <li v-for="sidebarItem in sidebarItems" :key="sidebarItem.id" class="item">
                    <div class="row gutter-width-xs">
                        <div class="col-3">
                            <router-link :to="sidebarItem.link">
                                <div class="img object-fit overflow-hidden">
                                    <div class="object-fit-cover transform-scale-h">
                                        <img :src="sidebarItem.imgUrl" :alt="sidebarItem.name">
                                    </div>
                                </div>
                            </router-link>
                        </div>

                        <div class="col-9 align-self-center">
                            <p class="item-t-head">
                                <router-link :title="sidebarItem.name" :to="sidebarItem.link">{{sidebarItem.name}}</router-link>
                            </p>
                        </div>
                    </div>
                </li>
            </ul>
        </div>

        <div class="widget widget_recent_comments">
            <h6 class="widget-title">Recent Comments</h6>

            <ul id="recentcomments">
                <li class="recentcomments">
                    <span class="comment-author-link">Tommy Andersen</span> on
                    <router-link title="Tommy Andersen" to="/news-single-post#comments">Lorem ipsum dolor sit amet, consectetur adipiscing elit…</router-link>
                </li>

                <li class="recentcomments">
                    <span class="comment-author-link">Rosie Ford</span> on
                    <router-link title="Rosie Ford" to="/news-single-post#comments">Lorem ipsum dolor sit amet, consectetur adipiscing elit…</router-link>
                </li>

                <li class="recentcomments">
                    <span class="comment-author-link">Arthur Hopin</span> on
                    <router-link title="Arthur Hopin" to="/news-single-post#comments">Lorem ipsum dolor sit amet, consectetur adipiscing elit…</router-link>
                </li>
            </ul>
        </div>

        <div class="widget widget_tag_cloud">
            <h6 class="widget-title">Tags</h6>

            <div class="tagcloud">
                <router-link title="Strategy" to="/news" class="tag-cloud-link">Strategy</router-link>
                <router-link title="Marketing" to="/news" class="tag-cloud-link">Marketing</router-link>
                <router-link title="Sales" to="/news" class="tag-cloud-link">Sales</router-link>
                <router-link title="Business" to="/news" class="tag-cloud-link">Business</router-link>
            </div>
        </div>
    </aside>
</template>

<script>
    import SidebarItems from '../../data/sidebar/sidebarItems.json';

    export default {
        name: 'Sidebar',
        data() {
            return {
                sidebarItems: SidebarItems.sidebarItems,
                urlAction: window.location.origin + this.$router.resolve( {
                    name: 'search-results',
                    params: { id: 1 }
                } ).href
            }
        }
    }
</script>
