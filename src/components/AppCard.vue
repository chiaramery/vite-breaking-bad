<script>
import { store } from "../store";
import ResultCharacters from "./ResultCharacters.vue";
export default {
    name: "AppCard",
    components: {
        ResultCharacters,
    },
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <ResultCharacters />
    <section class="row">
        <div class="card" v-for="character in store.characters" :key="character.char_id">
            <img :src="character.img" alt="">
            <h2>{{ character.name.toUpperCase() }}</h2>
            <div class="paragraph">
                <p>{{ character.category }}</p>
                <p>{{ character.status }}</p>
                <p> Nickname: {{ character.nickname }}</p>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
.row {
    margin-top: .5em;
    gap: 5px;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;

    .card {
        padding: .4em;
        width: calc(100% / 6);
        background-color: rgb(47 59 70);
        border: 1px solid black;

        img {
            padding: .2em;
        }

        h2 {
            text-align: center;
            color: white;
            font-size: .6em;
        }

        .paragraph {
            p {
                padding-top: 1em;
                color: gray;
                text-align: center;
                font-size: .7em;
            }

        }
    }
}
</style>