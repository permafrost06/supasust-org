<template>
    <div>
        <a href="#">
            <div class="container">
                <img src="~/assets/images/vf-photo-2.jpg" alt="">
                <h4>Headline: Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt.</h4>
            </div>
        </a>
    </div>
</template>

<script>
export default {
    name: 'vfSmall',
    props: ['img', 'caption']
}
</script>

<style lang="scss" scoped>
.container {
    background-color: rgba(0, 0, 0, 0.51);
    display: flex;
    align-items: center;
}

img {
    height: 20vh;
    object-fit: cover;
    padding: .75em;
}

h4 {
    padding: 0 1.5em 0 .5em;
}
</style>