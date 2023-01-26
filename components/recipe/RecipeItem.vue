<template>
  <div>
    <nuxt-link 
      class="recipes-content"
      tag="div"
      :to="{name: 'recipe-recipeId', params: {recipeId: recipe.id}}"
    >
      <img
        class="recipes-content__img"
        :alt="recipe.recipeTitle"
        :src="recipe.recipeImage"
      />
      <div class="recipes-content__body">
        <h1 class="recipes-content__body__title">
          {{ recipe.recipeTitle }}
        </h1>
        <div class="recipes-content__body__review">
          <img src="../../pages/images/heart.png" alt="Heart" />
          <p>{{ recipe.likes }} likes</p>
        </div>
      </div>
    </nuxt-link>
  </div>
</template>
<script>
export default {
  props: ["recipe"],
};
</script>
<style>
.recipes {
  display: flex;
  flex-wrap: wrap;
}

.recipes-content {
  background-color: #eef2e6;
  padding: 10px;
  margin: 13px 13px;
}

.recipes-content__body {
  padding: 5px;
}

.recipes-content__img {
  width: 280px;
  height: 210px;
}

.recipes-content__body__review {
  display: flex;
  align-items: center;
}

.recipes-content__body__review img {
  width: 20px;
  height: 20px;
  margin: 5px 10px 5px 0px;
}

.recipes-content__body__review p {
  margin: 0px;
}

.recipes-content__body__review img:hover {
  cursor: pointer;
}

.recipes-content__body__title {
  margin: 5px 0px;
  text-decoration: none;
  color: black;
  font-size: 30px;
  font-weight: bold;
  cursor: pointer;
}

.recipes-content__body__title:hover {
  text-decoration: underline red;
}
</style>
