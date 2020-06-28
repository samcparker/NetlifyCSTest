<template>
    <div>
        <header>
            <nav style="height: 75px" class="mb-5 navbar navbar-expand-sm navbar-light bg-light">
                    <div class="container">
                <a class="brand navbar-brand" href="/">{{ $site.title.toUpperCase() }}</a>
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
        </header>

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

    if (window.netlifyIdentity) {
    window.netlifyIdentity.on("init", user => {
      if (!user) {
        window.netlifyIdentity.on("login", () => {
          document.location.href = "/admin/";
        });
      }
    });
  }
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Anton&display=swap');

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

    .brand {
        font-family: 'Anton', sans-serif;
        font-size: 40px;
    }

</style>