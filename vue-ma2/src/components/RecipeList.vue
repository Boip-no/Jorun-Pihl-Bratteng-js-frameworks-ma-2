<template>
    <section>
        <Recipe
            v-for="(recipe, index) in recipes"
            v-bind:key="index"
            v-bind:title="recipe.title"
            v-bind:url="recipe.href"
            v-bind:ingredients="recipe.ingredients"
            v-bind:thumbnail="recipe.thumbnail"
        />
    </section>
</template>

<script>
import Recipe from "./Recipe";

export default {
    name: "Recipes",
    props: {
        recipes: Array
    },
    components: { Recipe }
};
</script>

<style scoped>
section {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
}
</style>
