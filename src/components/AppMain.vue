<script>

import axios from "axios";
import CharacterCard from './CharacterCard.vue';
import { store } from "../store.js"

    export default {

    name: "AppMain",

    components: {
        CharacterCard
    },
    data() {
        return {
            store,
            loaded: false,
        }
    },
    created(){
        axios.get("https://www.breakingbadapi.com/api/characters")
        .then((response) => {
            this.store.characters = response.data;
            console.log(this.store.characters);
            this.loaded = true;
        });
    }
    }
</script>

<template>
    <div>
        <div class="ms-container py-3">
            <div class="ms-container-sm px-3 py-2 d-flex align-items-center">
                <strong>Found {{ this.store.characters.length }} characters</strong>
            </div>
            <div class="ms-container-cards d-flex justify-content-between px-3 mt-3"
                v-if="this.loaded === true">

                <!-- Implementare Componente Card -->
               <CharacterCard v-for="character in this.store.characters"
                :info="character" />

            </div>
            <div class="ms-container-cards text-center px-3 mt-3"
                v-else>

                <i class="loading-icon fas fa-circle-notch"></i>

            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>

.ms-container{
    background-color: white;
}

.ms-container-sm{
    color: white;
    background-color: #212529;
}

.loading-icon{
    font-size: 3.75rem;
    margin-top: 6.25rem;
    margin-bottom: 6.25rem;
    animation: loading 1s linear infinite;
}

@keyframes loading {
    0% {
        transform: rotate(360deg);
    }
}

</style>