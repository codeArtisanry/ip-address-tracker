<template>
  <div class="container">
    <div class="d">
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
          style="width: 300px"
        />
        <button
          class="btn btn-dark my-2 my-sm-0 button-image"
          type="submit"
        ></button>
      </form>
      <LocationInfo
        :addresses="addresses"
        :ip="ip"
        :current_time="current_time"
      />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      addresses: [],
      ip: "",
      apikey: "ef3eeb9d020b49d19609313bc88ddb39",
      lat_lng: [37.4224, -122.08421],
      current_time: null,
    };
  },
  methods: {
    async onclick() {
      const res = await this.$axios.$get(
        "https://api.ipgeolocation.io/ipgeo?apiKey=" +
          this.apikey +
          "&ip=" +
          this.ip
      );
      this.addresses = res;
      this.current_time = this.addresses.time_zone.current_time;
      this.$router.push("/payal");
    },
  },
};
</script>
