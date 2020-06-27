<template>
    <div>
        <nav style="height: 75px" class="mb-5 navbar navbar-expand-sm navbar-light bg-light">
            <div class="container">
                <a class="navbar-brand" href="/">{{ $site.title }}</a>
                <button class="navbar-toggler d-lg-none" type="button" data-toggle="collapse"
                    data-target="#collapsibleNavId" aria-controls="collapsibleNavId" aria-expanded="false"
                    aria-label="Toggle navigation"></button>
                <div class="collapse navbar-collapse" id="collapsibleNavId">
                    <ul class="navbar-nav ml-auto mt-2 mt-lg-0">
                        <li class="nav-item">
                            <a class="nav-link" href="#">Showcase</a>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link" href="#">About</a>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link" href="#">Contact</a>
                        </li>
                    </ul>
                </div>
            </div>

        </nav>
        <div class="container">
            <Index v-if="isIndex" />
            <Single v-if="!isIndex" />
        </div>
        
    </div>
</template>

<script>
import Index from '../components/Index.vue';
import Single from '../components/Single.vue';
    export default {
        components: {
            Index, Single
            },
        computed: {
            isIndex() {
                return this.$page.path.endsWith("/");
            }
        }
    }
</script>

<style>

</style>