<template>
  <div class="container">
    <div class="second">
      <b-container class="bv-example-row">
        <b-row class="column-s">
          <b-col
            ><div class="f1">IP ADDRESS</div>
            <br /><b class="f2">{{ ip }}</b></b-col
          >
          <b-col
            ><div class="f1">LOCATION</div>
            <br /><b class="f2"
              >{{ addresses.city }}, {{ addresses.country_code2 }}<br />{{
                addresses.zipcode
              }}</b
            ></b-col
          >
          <b-col
            ><div class="f1">TIMEZONE</div>
            <br /><b class="f2">UTC -08:00</b></b-col
          >
          <b-col
            ><div class="f1">ISP</div>
            <br /><b class="f2">{{ addresses.isp }}</b></b-col
          >
        </b-row>
      </b-container>
    </div>
  </div>
</template>

<script>
export default {
  props: ["addresses", "ip", "current_time"],
};
</script>
