<script>
export default {
  data() {
    return {
      name: "PageTitle",
      title: 'Breaking Bad Api'
    }
  }
}
</script>

<template>
  <div class="d-flex my-1 mx-1">
    <img src="../assets/logo (2).png" alt="Page Logo">
    <h1 class="my-1">{{ title }}</h1>
  </div>
</template>

<style scoped>

h1{
  color: white;
}

img{
  margin-right: .3125rem;
  max-width: 3.125rem;
  max-height: 3.125rem;
  object-fit: cover;
  object-position: left;
}

</style>


