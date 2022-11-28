<script>

import axios from "axios";
import CharacterCard from './CharacterCard.vue';

    export default {

    name: "AppMain",

    components: {
        CharacterCard
    },
    data() {
        return {
            characters: [],
            loaded: false,
        }
    },
    created(){
        axios.get("https://www.breakingbadapi.com/api/characters")
        .then((response) => {
            this.characters = response.data;
            console.log(this.characters);
            this.loaded = true;
        });
    }
    }
</script>

<template>
    <div>
        <div class="ms-container py-3">
            <div class="ms-container-sm px-3 py-2 d-flex align-items-center">
                <strong>Found {{ this.characters.length }} characters</strong>
            </div>
            <div class="ms-container-cards d-flex justify-content-between px-3 mt-3"
                v-if="this.loaded === true">

                <!-- Implementare Componente Card -->
               <CharacterCard v-for="character in this.characters"
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