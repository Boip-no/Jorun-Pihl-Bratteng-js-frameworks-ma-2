<template>
    <div class="recipe">
        <h2>
            <a class="recipe-link" v-bind:href="url">{{ title }}</a>
        </h2>
        <img class="recipe-thumbnail" v-bind:src="thumbnail" />
        <div class="ingredients">
            {{ ingredients }}
        </div>
    </div>
</template>

<script>
export default {
    name: "Recipe",
    props: {
        title: String,
        url: String,
        ingredients: String,
        thumbnail: String
    }
};
</script>

<style>
.recipe {
    width: 280px;
    border: 1px solid lightgray;
    padding: 10px;
    margin-bottom: 15px;
}

.ingredients {
    text-align: left;
}

.recipe-thumbnail {
    width: 120px;
}

.recipe-link {
    display: block;
    color: darkred;
    text-decoration: none;
    margin-bottom: 12px;
}
</style>
