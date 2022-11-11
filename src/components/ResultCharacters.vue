<script>
import { store } from "../store";
export default {
    name: "ResultCharacters",
    data() {
        return {
            store
        }
    },
    computed: {
        characterNum() {
            return this.store.characters.length;
        }
    }
}
</script>

<template>
    <div class="large-container">
        <div class="founder">
            <h5> Found {{ characterNum}} characters </h5>
        </div>
    </div>

</template>

<style lang="scss" scoped>
.founder {
    padding: .6em;
    color: white;
    background-color: rgb(47 59 70);
}
</style>