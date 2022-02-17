<template>
  <div class="container">
    <div class="second">
      <b-container class="bv-example-row">
        <b-row class="col">
          <b-col :ipaddress="ip">IP ADDRESS<br />{{ ipaddress }}</b-col>
          <b-col>LOCATION</b-col>
          <b-col>TIMEZONE</b-col>
          <b-col>ISP</b-col>
        </b-row>
      </b-container>
    </div>
  </div>
</template>

<script>
export default {};
</script>
