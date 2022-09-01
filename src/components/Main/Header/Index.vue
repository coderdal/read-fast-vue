<template>
  <header>
    <div class="logo">
      <a href="#">
        <img src="assets/images/book_logo.png" alt="Book icon" />
        Read Fast
      </a>
    </div>
  </header>
</template>

<script>
export default { name: "appHeader" };
</script>

<style scoped>
main header {
  width: 100%;
  height: 100px;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
}

main header .logo a {
  width: 185px;
  height: 100%;
  display: flex;
  align-items: center;
  flex-direction: row;
  justify-content: space-around;
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
  text-decoration: none;
  color: var(--text-color);
  font-weight: 800;
  font-size: 1.2em;
}

main header .logo img {
  width: 80px;
  height: 60px;
}
</style>
