<template>
    <div>
        <header class="">
            <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <div class="container">
        <a class="navbar-brand brand d-none d-md-block" href="/">LUCA'S PORTFOLIO</a>
        <a class="navbar-brand brand-sm d-md-none" href="/">LUCA'S PORTFOLIO</a>
    
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#collapsibleNavbar" aria-controls="collapsibleNavbar" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>

        <div class="collapse navbar-collapse" id="collapsibleNavbar">
          <ul class="navbar-nav mr-auto nav-links">
            <li class="nav-item">
              <a class="nav-link" href="/">SHOWCASE</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="/about">ABOUT</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="/contact">CONTACT</a>
            </li>
          </ul>
        </div>
      </div>
    </nav>
        </header>
        <div style="min-height: 0px; width: 100%"></div>
        <main role="main" class="container">
            <Index v-if="getPage() == 'index'" />
            <Single v-if="getPage() == 'single'" />
            <About v-if="getPage() == 'about'" />
            <Contact v-if="getPage() == 'contact'" />
        </main>
        <div style="min-height: 50px; width: 100%"></div>
        <!-- <footer>
            <div class="container">
                

            </div>
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
        </footer> -->

        <footer class="footer">
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
    import About from '../components/About.vue';

    export default {
        components: {
            Index,
            Single, About
        },
        data: () => { return {
            config: null
        }},
        methods: {
            getConfig() {
                this.$site.pages.forEach(element => {
                    if (element.relativePath == "index.md") {
                        this.config = element;
                        console.log(this.config);
                        return;
                    }
                    
                });
            },
             getPage() {
                var page = this.$page;
                console.log(page.relativePath);
                if (page.relativePath.startsWith("index")) {
                    return "index";
                }
                if (page.relativePath.startsWith("about")) {
                    console.log(page);
                    return "about";
                }
                if (page.relativePath.startsWith("contact")) {
                    return "contact";
                }
                return "single";
            }
        },
        mounted () {
            this.getConfig();
        }
    }
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Oswald:wght@200;400&display=swap');


html {
  position: relative;
  min-height: 100%;
}
body {
  margin-bottom: 60px; /* Margin bottom by footer height */
}
.footer {
  position: absolute;
  bottom: 0;
  width: 100%;
  height: 30px; /* Set the fixed height of the footer here */
  line-height: 30px; /* Vertically center the text there */
  background-color: #f5f5f5;
}


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

    .brand-sm {
        font-family: 'Anton', sans-serif;
        font-size: 30px;
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