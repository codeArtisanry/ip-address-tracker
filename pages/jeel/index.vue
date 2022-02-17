<template>
  <div>
    <Header
      v-model="ipAddress"
      :ip-address="ipAddress"
      :get-ip-data="getIpData"
    />
    <Middledata :ip-data="ipData" />
  </div>
</template>

<script>
export default {
  name: "IndexPage",
  data() {
    return {
      ipAddress: "",
      ipData: {
        ip: "",
        location: {
          country: "",
          region: "",
          timezone: "",
        },
        isp: "",
      },
    };
  },
  methods: {
    async getIpData() {
      const res = await this.$axios.$get(
        "https://geo.ipify.org/api/v2/country,city?apiKey=at_5jNicfri3nLpD3hOwy9LnQVQ89cf7&ipAddress=" +
          this.ipAddress
      );
      this.ipData = res;
    },
  },
};
</script>
<style scoped>
.middle-div {
  display: flex;
  position: relative;
  z-index: 1;
  background: white;
  box-shadow: 0 0 20px 0 rgb(0 0 0 / 50%);
  border-radius: 0.7em;
  bottom: 70px;
  margin: auto 15%;
  padding: 5% auto;
}

.rline {
  border-style: none;
}
</style>
