<template>
    <div>
      <main>
        <div class="recipes-detail">
          <img
            class="recipes-detail__img"
            alt="Pasta"
            :src="recipe.recipeImage"
          />
          <h1 class="recipes-detail__title">
            {{ recipe.recipeTitle }}
          </h1>
          <p class="recipes-detail__body">
            {{ recipe.body }}
          </p>
        </div>
      </main>
    </div>
  </template>
  <script>
  export default {
    asyncData({store, params}) {
        const recipe = store.getters.detailRecipe(params.recipeId)
        return { recipe }
    },
  }
  </script>
  <style>
  .recipes-detail {
    display: flex;
    justify-content: center;
  }
  
  .recipes-detail div {
    width: 600px;
  }
  
  .recipes-detail__img {
    width: 400px;
    height: 300px;
    display: block;
    text-align: center;
    margin: 0px auto;
  }
  
  .recipes-detail__title {
    text-align: center;
  }
  </style>
  