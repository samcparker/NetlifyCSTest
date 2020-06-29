<template>
    <div>

        <img :src="$page.frontmatter.image" />


  
        <h2 class="title">
            {{ $page.frontmatter.title.toUpperCase() }}
        </h2>

        <Content />
    </div>
</template>

<script>
    export default {
        mounted() {
            console.log(this.$page.frontmatter);
        },
        computed: {
            // getSrc() {
            //     // if image location begins with a '.' then it's relative, else it's a direct link
            //     if (this.$page.frontmatter.image.startsWith(".")) {
            //         return '.' + this.$page.frontmatter.image;
            //     }
            //     return this.$page.frontmatter.image;
            // }
        }
    }
</script>

<style scoped>
 img {
     width: 100%;
     height: 500px;
     object-fit: cover;
 }

</style>