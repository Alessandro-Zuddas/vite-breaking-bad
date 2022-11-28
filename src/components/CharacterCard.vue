<script>
    export default {
        name: "CharacterCard",
    }
</script>

<template>
  
    <div class="character-card py-3 mb-3 d-flex flex-column text-center">
        <img src="" alt="Character Image">
        <strong class="character-name my-2">Nome Personaggio</strong>
        <small class="infos">Nome serie</small>
        <small class="infos">Stato</small>
    </div>
   
</template>

<style lang="scss" scoped>

.character-card{
    width: calc(100% / 5 - 1.25rem);
    margin-right: 1.25rem;
    background-color: #2e3a46;
}

.character-name{
    color: white;
}

.infos{
    color: #77756d;
}

</style>