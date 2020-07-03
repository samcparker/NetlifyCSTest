<template>
    <div class="pt-5 mt-5 ">
        <h2 class="text-center pb-5 mb-5">You can get in touch with me by email here:</h2>

        <div class="row text-center mb-5">
            <div class="col-md mb-5">
                <img src="https://image.flaticon.com/icons/png/512/8/8807.png">
                <h2> {{ $page.frontmatter.email }}</h2>
            </div>
        </div>
    </div>
</template>

<script>
    export default {

    }
</script>

<style scoped>
img {
    width: 20%;
    height: auto;
}
</style>