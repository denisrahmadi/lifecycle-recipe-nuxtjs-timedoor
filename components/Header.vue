<template>
    <div>
        <header class="header">
          <h1 class="header-title">Food Recipes</h1>
          <nav class="header-nav">
            <nuxtLink tag="button" to="/" class="header-nav__link">
              Home 
            </nuxtLink>
            <nuxtLink tag="button" to="/add" class="header-nav__link">
              Add Recipes
            </nuxtLink>
          </nav>
        </header>
    </div>
</template>
<script>
export default {};
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
</style>
