<template>
  <div>
    <client-side>
      <div id="map-wrap" style="height: 92.7vh" class="z-0">
        <l-map :zoom="7" :center="lat_lng">
          <l-tile-layer
            url="http://{s}.tile.osm.org/{z}/{x}/{y}.png"
          ></l-tile-layer>
          <l-marker :lat-lng="lat_lng">
            <img :src="require(`@/static/icon-location.svg`)" />
          </l-marker>
        </l-map>
      </div>
    </client-side>
  </div>
</template>

<script>
export default {
  props: {
    // eslint-disable-next-line vue/prop-name-casing
    lat_lng: {
      type: Array,
      // eslint-disable-next-line vue/require-valid-default-prop
      default: [62.22875562830978, 99.40894012301204],
    },
  },
};
</script>
