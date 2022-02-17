<template>
  <div>
    <header>
      <div class="search">
        <input
          type="text"
          placeholder="Search for any IP Address"
          :value="domain"
          @input="$emit('input', $event.target.value)"
        />
        <button @click="fetchIpInfo">
          <img :src="require('@/static/icon-arrow.svg')" alt="arrow icon" />
        </button>
      </div>
    </header>
  </div>
</template>

<script>
export default {
  props: {
    domain: {
      type: String,
      default: "",
    },
    fetchIpInfo: {
      type: String,
      default: "",
    },
  },
};
</script>

<style>
header {
  display: flexbox;
  position: relative;
  text-align: center;
}

.search {
  display: flex;
  display: inline-flex;
  position: relative;
  z-index: 1;
  bottom: 15em;
}

.search input,
.search button {
  border: 0;
  outline: 0;
  padding: 1.5em;
}

.search input {
  width: 35em;
  border-bottom-left-radius: 0.9em;
  border-top-left-radius: 0.9em;
}

.search button {
  background: black;
  cursor: pointer;
  border-top-right-radius: 0.9em;
  border-bottom-right-radius: 0.9em;
}
</style>
