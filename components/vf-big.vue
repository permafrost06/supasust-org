<template>
    <div class="container">
        <a href="#">
            <div></div>
            <h3>Headline: Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt.</h3>
        </a>
    </div>
</template>

<script>
export default {
    name: 'vfBig',
    props: ['img', 'caption']
}
</script>

<style lang="scss" scoped>
.container {
    background-image: url("~assets/images/vf-photo-1.jpg");
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
}

a {
    display: flex;
    flex-direction: column;
    height: 100%;

    div {
        flex: 1;
    }
}

h3 {
    padding: 1em;
    background-color: rgba(0, 0, 0, 0.51);
}
</style>