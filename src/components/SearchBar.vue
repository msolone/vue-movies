<template>
    <section class="search_bar">
        <section>Search for your Movie</section>
        <input type=text placeholder="Search by Movie Title"/>
    </section>
    
</template>

<script>
export default {
  name: "SearchBar"
};
</script>

<style scoped>
.search_bar {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 80%;
}

input {
    height: 2em;
    width: 30em;
}


</style>
