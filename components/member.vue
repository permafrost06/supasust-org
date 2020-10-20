<template>
    <div class="container">
        <img src="~/assets/images/blank-profile.jpg" alt="" height="250px">
        <div class="backdrop">
            <h3>Adila Zaman</h3>
            <div>Vice-President</div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'member',
    props: ['name', 'designation']
}
</script>

<style lang="scss" scoped>
.container {
    position: relative;
}

.backdrop {
    position: absolute;
    bottom: 4px;
    padding: 1em 1em 1.5em 1em;
    width: 250px;
    background-color: rgba(0, 0, 0, 0.51);
}
</style>