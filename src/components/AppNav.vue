<script>
    export default {
        name: "AppNav",
    }
</script>

<template>
    <div class="ms-container mt-5 mb-4 d-flex align-items-end">
        <select class="category-select" name="category-select" id="category-select">
            <option value="" disabled selected>Select category</option>
            <option value="">Prova</option>
            <option value="">Prova</option>
        </select>
    </div>
</template>

<style lang="scss" scoped>

.category-select{
    margin-left: .625rem;
    padding: .3125rem .625rem;
    border-radius: .3125rem;
}

</style>