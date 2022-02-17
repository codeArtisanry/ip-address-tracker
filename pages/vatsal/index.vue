<template>
  <div>
    <top-header />
    <the-search-bar
      v-model="domain"
      :domain="domain"
      :fetch-ip-info="fetchIpInfo"
    />
    <div class="ip-info">
      <ip-info :title="'ip address'" :value="domaindata.ip" />
      <ip-info
        :title="'location'"
        :value="
          domaindata.location.country +
          `,` +
          domaindata.location.region +
          ',' +
          domaindata.location.postalCode
        "
      />
      <ip-info
        :title="'time zone'"
        :value="`UTC` + domaindata.location.timezone"
      />
      <ip-info :title="'isc'" :value="domaindata.isp" />
    </div>
    <div class="map">
      <the-map :lat_lng="lat_lng" />
    </div>
  </div>
</template>

<script>
import IpInfo from "~/components/IpInfo.vue";
import TheMap from "~/components/TheMap.vue";
import TheSearchBar from "~/components/TheSearchBar.vue";
import TopHeader from "~/components/TopHeader.vue";
export default {
  components: { TopHeader, IpInfo, TheMap, TheSearchBar },
  data() {
    return {
      domain: "",
      domaindata: {
        ip: "",
        location: {
          country: "",
          postalCode: "",
          timezone: "",
          region: "",
        },
        isp: "",
      },
      lat_lng: [22.88437411656432, 76.80039181936634],
    };
  },
  methods: {
    async fetchIpInfo() {
      const results = await this.$axios.$get(
        `https://geo.ipify.org/api/v2/country,city?apiKey=at_B2ObKjCqbg52lMW2XRHCHusAZwlRV&ipAddress=` +
          this.domain
      );
      this.domaindata = results;
      this.lat_lng = [
        this.domaindata.location.lat,
        this.domaindata.location.lng,
      ];
      // lat=,this.domaindata.location.lat,
      // lng=this.domaindata.location.lng
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Karla:wght@500&family=Rubik:wght@400;500;700&display=swap");

body {
  font-family: Rubik, sans-serif;
  font-weight: 700;
}

.ip-info {
  display: flex;
  z-index: 2;
  height: 12em;
  background: white;
  box-shadow: 5px 10px 20px 2px rgb(0 0 0 / 50%);
  border-radius: 1em;
  margin: auto 15%;
  position: relative;
  bottom: 10em;
  padding: 1em;
}

.ip-info-card:nth-of-type(4) {
  border-right-style: none;
  padding-right: 2.5em;
  padding-bottom: 1em;
}

.ip-info-card:nth-of-type(2) {
  padding-right: 2.5em;
}

.map {
  position: relative;
  bottom: 16.5em;
  z-index: 0;
}
</style>
