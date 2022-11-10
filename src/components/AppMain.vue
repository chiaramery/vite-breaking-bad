<script>
import AppCard from './AppCard.vue';
import { store } from "../store";
export default {
    name: "AppMain",
    components: {
        AppCard,
    },
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <main>
        <div class="container">
            <AppCard :character="character" />

        </div>
    </main>
</template>

<style lang="scss" scoped>

</style>