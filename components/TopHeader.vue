<template>
  <header>
    <h1>IP Address Tracker</h1>
    <div class="search">
      <input type="text" placeholder="Search for any IP Address" />
      <button>
        <img :src="require('@/static/icon-arrow.svg')" alt="arrow icon" />
      </button>
    </div>
  </header>
</template>

<script>
export default {};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Karla:wght@500&family=Rubik:wght@400;500;700&display=swap");

header {
  background-image: url("@/static/pattern-bg.png");
  background-size: cover;
  text-align: center;
  color: white;
  height: 300px;
}

h1 {
  padding-top: 0.7em;
}

.text-decor {
  font-family: Rubik, sans-serif;
  font-weight: 700;
}

.search {
  display: inline-flex;
}

.search input,
.search button {
  border: 0;
  outline: 0;
  padding: 1em;
}

.search input {
  width: 40em;
  border-bottom-left-radius: 0.7em;
  border-top-left-radius: 0.7em;
}

.search button {
  background: black;
  cursor: pointer;
  border-top-right-radius: 0.7em;
  border-bottom-right-radius: 0.7em;
}
</style>
