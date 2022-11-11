<script>
import { store } from "../store";
export default {
    name: "AppSelect",
    data() {
        return {
            store,
            categoryOptions: ["Breaking Bad", "Better Call Saul"]
        }
    }
}
</script>

<template>
    <div class="select-container">
        <div class="select">
            <select name="select" class="form-select" id="select" v-model="store.searchCategory">
                <option selected value="">Select category</option>
                <option v-for="(option, index) in categoryOptions" :value="option" :key="index"> {{ option }}</option>
            </select>
            <button class="btn" @click="$emit('selectCategory')"> Select </button>
        </div>

    </div>
</template>

<style lang="scss" scoped>
.select-container {
    width: 60%;
    margin: 0 auto;
    padding: 2em;

    .select {
        select {
            padding: .5em 1em;
        }
    }

    .btn {
        padding: .5em;
        color: white;
        background-color: rgb(47 59 70);
        border: 1px solid white;
        cursor: pointer;
    }
}
</style>