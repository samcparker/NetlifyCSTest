<template>
  <div class="mt-5">
      <center><img class="rounded-circle" :src="$page.frontmatter.image">
        <h2 class="mt-3 mb-4">{{ $page.frontmatter.about_name }}</h2></center>
        <hr class="mt-5">
      <Content class="mt-5" />
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
    img {
        width: 200px;
        height: 200px;
        object-fit: cover;
    }
</style>