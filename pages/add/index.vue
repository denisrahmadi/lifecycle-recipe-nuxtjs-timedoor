<template>
  <div class="body">
    <main>
      <div class="add-recipe">
        <label>
          <b>IMAGE LINK : </b>
          <input
            v-model="newRecipe.recipeImage"
            type="text"
            placeholder="https://www.image.com/..."
            class="add-recipe__img"
          />
        </label>
        <input
          v-model="newRecipe.recipeTitle"
           type="text" placeholder="Title ..." class="add-recipe__title" />
        <hr />
        <textarea
          v-model="newRecipe.body"
          placeholder="Your Recipe ....."
          class="add-recipe__desc"
        ></textarea>
        <button class="add-recipe__button" @click="addRecipe">Add Recipe</button>
      </div>
      {{ newRecipe }}
    </main>
  </div>
</template>
<script>
import axios from 'axios'

export default {
  data() {
    return {
      newRecipe: {
        recipeImage: "",
        recipeTitle: "",
        likes: 0,
        body: ""
      }
    }
  },
  methods: {
    addRecipe(){
      // let newId = this.$store.getters.lastIdRecipe + 1
      // this.$store.commit('addNewRecipe', {id: newId, ...this.newRecipe})
      // this.$router.push("/")

      // axios.post(
      //   "https://nuxtjs-timedoor-default-rtdb.asia-southeast1.firebasedatabase.app/recipes.json", this.newRecipe
      //   ).then(response => {
      //     console.log(response);
      //     this.$router.push("/")
      //   })

      this.$store.dispatch("addRecipe", this.newRecipe)
        .then (() => this.$router.push("/")) 
    }
  }
};


</script>
<style>
.body {
  margin: 0px;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-left: 40px;
  padding-right: 40px;
  background-color: #eef2e6;
}

main {
  margin: 22px;
}

.recipes {
  display: flex;
  flex-wrap: wrap;
}

.header-nav__link {
  margin-left: 20px;
  color: black;
  text-decoration: none;
  font-size: 20px;
}

/* Recipe Content */
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
}

/* Add Recipe */
.add-recipe__title,
.add-recipe__desc {
  display: block;
  width: 100%;
  margin: 10px 0px;
  border: none;
}

.add-recipe__title {
  height: 50px;
  font-size: 25px;
}

.add-recipe__desc {
  height: 300px;
}

.add-recipe__img {
  border: none;
  height: 30px;
}

.add-recipe__button {
  color: white;
  background-color: #4b56d2;
  border: none;
  padding: 20px;
  border-radius: 15px;
  font-weight: bold;
}

.add-recipe__button:hover {
  cursor: pointer;
  background-color: #82c3ec;
  color: #4b56d2;
}

/* Detail */
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
