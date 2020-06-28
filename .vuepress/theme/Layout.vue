<template>
    <div>
        <header class="">
            <nav style="height: 100px" class="mb-5 navbar navbar-expand-sm navbar-light bg-light">
                    <div class="container">
                <a class="brand navbar-brand" href="/">{{ $site.title.toUpperCase() }}</a>
                <button class="navbar-toggler d-lg-none" type="button" data-toggle="collapse"
                    data-target="#collapsibleNavId" aria-controls="collapsibleNavId" aria-expanded="false"
                    aria-label="Toggle navigation"></button>
                <div class="collapse navbar-collapse nav-links" id="collapsibleNavId">
                    <ul class="navbar-nav ml-auto mt-2 mt-lg-0">
                        <li class="nav-item">
                            <a class="nav-link" href="#">SHOWCASE</a>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link" href="#">ABOUT</a>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link" href="#">CONTACT</a>
                        </li>
                    </ul>
                </div>
</div>


            </nav>
        </header>
        <div style="min-height: 0px; width: 100%"></div>
        <main role="main" class="container">
            <Index v-if="isIndex" />
            <Single v-if="!isIndex" />
        </main>
        <div style="min-height: 50px; width: 100%"></div>
        <footer>
            <!-- <div class="container">
                

            </div> -->
            <div class="jumbotron jumbotron-fluid mb-0">
                <div class="container">
                
                    <div class="row">
                        <div class="col-sm w-100">
                        <span class="text-muted">Contact Luca @ <a href="#">luca@gmail.com</a></span>
                    </div>
                    <div class="col-sm text-right w-100">
                        <span class="text-muted">Website made by <a href="https://www.samcparker.co.uk">Sam
                                Parker</a></span>
                    </div>
                    
                </div>
                </div>
            </div>
        </footer>

    </div>
</template>

<script>
    import Index from '../components/Index.vue';
    import Single from '../components/Single.vue';
    export default {
        components: {
            Index,
            Single
        },
        computed: {
            isIndex() {
                return this.$page.path.endsWith("/");
            }
        }
    }
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Oswald:wght@200;400&display=swap');


    html {
        overflow-y: scroll;
        position: relative;
        min-height: 100%;
    }

    h1 {
        font-family: 'Anton', sans-serif;
        /* letter-spacing: 2px; */
        font-size: 40px;
        
    }

    h2 {
        font-family: 'Oswald', sans-serif;
        font-size: 40px;
        font-weight: 200;
    }

    .brand {
        font-family: 'Anton', sans-serif;
        font-size: 40px;
        font-weight: 400;
        letter-spacing: 4px;
    }

    .nav-links {
        font-family: 'Oswald', sans-serif;
        font-size: 25px;
        font-weight: 200;
        /* font-size: 40px; */
        /* font-weight: 10; */
    }

    
</style>