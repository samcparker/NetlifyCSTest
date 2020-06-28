<template>
    <div>
        <div class="mb-5 pt-3" v-for="post in posts">
            <h2 style="" class="mb-2">
                {{ post.title.toUpperCase() }}
            </h2>
            <div class="parent ">
                <img :src="post.frontmatter.image" />
                <a :href="post.path">
                    <div class="overlay">
                        <!--  -->
                    </div>
                </a>
            </div>
            
        </div>
    </div>
</template>

<script>
    export default {
        computed: {
            posts() {
                var pages = this.$site.pages;
                
                var filtered_sorted = pages.filter(page => page.path.startsWith("/_posts/") && page.path.endsWith(".html")).sort((a,
                    b) => { return new Date(b.frontmatter.date).getTime() - new Date(a.frontmatter.date).getTime() });
 
                return filtered_sorted;
            }
        }
    }
</script>

<style scoped>
    .parent {
        position: relative;
        height: 200px;
        transition-duration: 1s;
    }

    .parent img {
        position: absolute;
        width: 100%;
        height: 100%;
        object-fit: cover;

    }

    .parent .overlay {
        padding-left: 10px;
        padding-top: 5px;
        position: absolute;
        width: 100%;
        height: 100%;
        color: white;
        background-image: linear-gradient(to top, rgba(255, 255, 255, 0.3), rgba(255, 0, 0, 0));
        transition-duration: 1s;
        font-family: Arial, Helvetica, sans-serif;
        font-weight: bold;
        font-size: 50px;
        transition: 1s;

    }

    .parent .overlay p {

        transition: 1s;
    }

    .parent .overlay:hover {
        opacity: 0.4;
        padding-left: 20px;
    }

    .parent:hover {
        height: 500px;
    }

    h1 {
        font-family: 'Anton', sans-serif;
    }
</style>