<script>
    export default {
        name: "CharacterCard",
        props: {
            info: Object,
        }
    }
</script>

<template>
  
    <div class="character-card py-3 mb-3 d-flex flex-column text-center">
        <img :src="info.img" :alt="info.name">
        <strong class="character-name my-2">{{ info.name }}</strong>
        <small class="card-infos">{{ info.category }}</small>
        <small class="card-infos">{{ info.status }}</small>
    </div>
   
</template>

<style lang="scss" scoped>

.character-card{
    width: calc(100% / 5 - 1.25rem);
    margin-right: 1.25rem;
    padding: 0 .625rem;
    background-color: #2e3a46;
}

.character-name{
    color: white;
}

.card-infos{
    color: #77756d;
}

img{
    max-width: 12.5rem;
    max-height: 15.625rem;
}

</style>