<template>
    <div>
        <div class="mb-5" v-for="post in posts">
            <!-- <h1><a :href="post.path">{{ post.title }}</a></h1> -->
            <!-- <a :href="post.path">
                
                <img :src="post.frontmatter.image" class="img-fluid ${3|rounded-top,rounded-right,rounded-bottom,rounded-left,rounded-circle,|}" alt="">
            </a> -->
            <div class="parent">
                <img :src="post.frontmatter.image"
                    />
                <a :href="post.path"><div class="overlay">
                    <p >
                        {{ post.title.toUpperCase() }}
                        </p></div></a>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        computed: {
            posts() {
                var pages = this.$site.pages;
                return pages.filter(page => page.path.startsWith("/_posts/") && page.path.endsWith(".html"));
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
    position: absolute;
    width: 100%;
    height: 100%;
    color: white;
    background-image: linear-gradient(to top, rgba(128,0,128,0.5), rgba(255,0,0,0));
    transition-duration: 1s;
    font-family: Arial, Helvetica, sans-serif;
    font-weight: bold;
    font-size: 50px;
    
}

.parent .overlay p {
    mix-blend-mode: difference;
}

.parent .overlay:hover {
    opacity: 0.6;
    padding-left: 20px;
}

.parent:hover {
    height: 300px;
}
</style>