<template>
    <div class="container">
        <p v-if="loading">Loading...</p>
        <RecipeList v-bind:recipes="recipes" />
    </div>
</template>

<script>
import RecipeList from "./components/RecipeList";

export default {
    name: "App",
    data() {
        return {
            // loading will be set to false after the API call finishes (in the second then method)
            loading: true,
            recipes: null
        };
    },
    components: {
        RecipeList
    },
    mounted() {
        fetch("https://cors-anywhere.herokuapp.com/http://www.recipepuppy.com/api")
            .then(response => response.json())
            .then(json => {
                this.recipes = json.results;
                this.loading = false;
            })
            .catch(() => {
                // handle error
            });
    }
};
</script>

<style>
body {
    background: #ebebeb;
    font-family: sans-serif;
}

.container {
    width: 90%;
    max-width: 1200px;
    margin: 0 auto;
    background: white;
    padding: 15px;
}
</style>
