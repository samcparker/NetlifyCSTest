<template>
    <div>
        <div class="mb-5 " v-for="post in posts">
            <h1 style="font-family: Anton, sans-serif" class="mb-0">
                {{ post.title.toUpperCase() }}
            </h1>
            <div class="parent shadow-md  ">
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
                filtered_sorted.forEach(element => {
                    console.log(new Date(element.frontmatter.date).getTime());
                });
                return filtered_sorted;
            }
        }
    }
</script>

<style scoped>
    .parent {
        position: relative;
        height: 150px;
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
        background-image: linear-gradient(to top, rgba(128, 0, 128, 0.5), rgba(255, 0, 0, 0));
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
        opacity: 0.6;
        padding-left: 20px;
    }

    .parent:hover {
        height: 500px;
    }

    h1 {
        font-family: 'Anton', sans-serif;
    }
</style>