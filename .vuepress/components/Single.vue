<template>
    <div>
        <div class="parent">
            <img :src="$page.frontmatter.image" />

                <div class="overlay">
                    <p class="title">
                        {{ $page.frontmatter.title.toUpperCase() }}
                    </p>
                    <p class="lead">
                        Location: Unknown<br>
                        Temperature: 17 C
                    </p>
                </div>
       
        </div>
    </div>
</template>

<script>
    export default {

    }
</script>

<style scoped>
    .parent {
        position: relative;
        height: 400px;
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

        font-family: Arial, Helvetica, sans-serif;
        font-weight: bold;
        font-size: 50px;
        mix-blend-mode: difference;
    }


</style>