<script>

import axios from "axios";
import { onUpdated } from "vue";
import { store } from "../store.js"

export default {
    name: "AppNav",

    data() {
        return {
            store,
            loaded: false,
        }
    },
    methods:{
        onSelectClick(){
            if(store.categoryValue === "breaking"){
                axios.get("https://www.breakingbadapi.com/api/characters?category=Breaking+Bad")
                .then((response) => {
                    this.store.characters = response.data;
                    console.log(this.store.characters);
                    this.loaded = true;
                });
            }else if(store.categoryValue === "betterCallSaul"){
                axios.get("https://www.breakingbadapi.com/api/characters?category=Better+Call+Saul")
                .then((response) => {
                    this.store.characters = response.data;
                    console.log(this.store.characters);
                    this.loaded = true;
                });
            }else if(store.categoryValue === "all"){
                axios.get("https://www.breakingbadapi.com/api/characters")
                .then((response) => {
                    this.store.characters = response.data;
                    console.log(this.store.characters);
                    this.loaded = true;
                });
            }
        }
    }
}
</script>

<template>
    <div class="ms-container mt-5 mb-4 d-flex align-items-end">
        <form action="">
            <label class="label">Select category:
                <select class="category-select" name="category-select" id="category-select"
                 v-model="store.categoryValue" @change="onSelectClick">
                    <option value="all" selected>All</option>
                    <option value="breaking">Breaking Bad</option>
                    <option value="betterCallSaul">Better Call Saul</option>
                </select>
            </label>
        </form>
    </div>
</template>

<style lang="scss" scoped>

.category-select{
    margin-left: .625rem;
    padding: .3125rem .625rem;
    border-radius: .3125rem;
}

.label{
    color: white;
}

</style>