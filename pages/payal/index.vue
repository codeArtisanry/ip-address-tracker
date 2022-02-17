<template>
  <div class="container d">
    <h4 class="title"><b>IP Address Tracker</b></h4>
    <form
      id="form"
      class="form-inline form"
      method="post"
      @submit.prevent="onclick"
    >
      <input
        v-model="ip"
        class="form-control mr-lg-6 textbox"
        type="search"
        placeholder="Search for any IP addresses or domain"
      />
      <button
        class="btn btn-dark my-2 my-sm-0 button-image"
        type="submit"
      ></button>
    </form>
    <LocationInfo />
  </div>
</template>

<script>
export default {};
</script>
