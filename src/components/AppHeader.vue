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
        width: 90%;
        margin: 1em auto;
        padding: 1.5em;
        display: flex;
        align-items: center;
        background-color: white;
        box-shadow: 5px 10px black;


        .logo {
            margin-right: 1em;
            width: 100px;
        }

        .title {
            color: rgb(47 59 70);
        }
    }

}
</style>