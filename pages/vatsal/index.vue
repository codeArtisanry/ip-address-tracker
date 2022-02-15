<template>
  <div>
    <top-header />
    <div class="ip-info">
      <ip-info :title="'ip address'" :value="'abc'" />
      <ip-info :title="'location'" :value="'abc'" />
      <ip-info :title="'time zone'" :value="'abc'" />
      <ip-info :title="'isc'" :value="'abc'" />
    </div>
    <div class="map"></div>
  </div>
</template>

<script>
import IpInfo from "~/components/IpInfo.vue";
import TopHeader from "~/components/TopHeader.vue";
export default {
  components: { TopHeader, IpInfo },

  data() {
    return {};
  },
};
</script>

<style>
.ip-info {
  display: flex;
  z-index: 2;
  height: 10em;
  background: white;
  box-shadow: 0 0 20px 0 rgb(0 0 0 / 50%);
  grid-column: 2/3;
  grid-row: 2/4;
  border-radius: 0.7em;
  width: 50%;
  margin-left: 25%;
}

.ip-info ip-info-card {
  flex: 1;
  display: absolute;
}

.ip-info-card:nth-of-type(2) {
  background-color: tomato;
}
</style>
