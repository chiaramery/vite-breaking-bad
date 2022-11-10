<script>
export default {
    name: "AppHeader"
}
</script>

<template>
    <header>
        <div class="wrapper">
            <div class="logo">
                <img src="../assets/img/breaking-bad-logo.png" alt="">
            </div>
            <div class="title">
                <h1>Breaking Bad Api</h1>
            </div>
        </div>
    </header>
</template>

<style lang="scss" scoped>
header {
    width: 100%;

    .wrapper {
        width: 100%;
        padding: 1.5em;
        display: flex;
        align-items: center;

        .logo {
            margin-right: 1em;
            width: 100px;
        }

        .title {
            color: white;
        }
    }

}
</style>