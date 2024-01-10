<script>
export default {
    name: "AppHeader"
}
</script>
<template lang="">
    <header>
        <div class="container-logo-title d-flex">
            <img src="https://4.bp.blogspot.com/-aQgkqbEBQT8/Voq3RbKokzI/AAAAAAAACdo/pS7sxosX5BA/s1600/Logo%2BYu-Gi-Oh%2521%2B03.png" alt="yugioh-logo">
            <h1>Yu-Gi-Oh Api</h1>
        </div>
    </header>
</template>
<style lang="scss" scoped>
header {
    background-color: white;
    padding: 30px 20px;

    .container-logo-title {
        align-items: center;

        img {
            width: 100px;
            margin-right: 20px;
        }

        h1 {
            font-size: 50px;
        }
    }
}
</style>