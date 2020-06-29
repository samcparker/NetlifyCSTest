<template>
    <div>

        <img class="title-img mt-5" :src="$page.frontmatter.image" />


  
        <h2 class="title mt-5">
            {{ $page.frontmatter.title.toUpperCase() }}
        </h2>

        <Content class="content" style="max-width: 100%;" />
    </div>
</template>

<script>
    export default {

    }
</script>

<style >
 .title-img {
     width: 100%;
     min-width: 100%;
     max-width: 100%;
     height: 500px;
     object-fit: cover;
 }

 .content img {


     max-width: 100%;
    width: 50%;
     object-fit: cover;
     height: auto;
     transition-duration: 1s;
 }

  .content img:hover {
   
    width: 100%;

     object-fit: cover;
     height: auto;
 }

</style>