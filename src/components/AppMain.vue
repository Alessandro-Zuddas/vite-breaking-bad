<script>

import CharacterCard from './CharacterCard.vue';

    export default {
        name: "AppMain",

        components: {
            CharacterCard
        }
    }
</script>

<template>
    <div>
        <div class="ms-container py-3">
            <div class="ms-container-sm px-3 py-2 d-flex align-items-center">
                <strong>Found --- characters</strong>
            </div>
            <div class="ms-container-cards d-flex justify-content-between px-3 mt-3">

                <!-- Implementare Componente Card -->
               <CharacterCard />

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

</style>