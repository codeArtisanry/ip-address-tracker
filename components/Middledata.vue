<template>
  <div class="middle-div row">
    <div class="middle-input-div col-lg-3 col-sm-12">
      <label class="middle-label">IP ADDRESS</label>
      <h1 class="middle-input">{{ ipData.ip }}</h1>
    </div>
    <div class="middle-input-div col-lg-3 col-sm-12">
      <label class="middle-label">LOCATION</label>
      <h1 class="middle-input">
        {{ ipData.location.country + " " + ipData.location.region }}
      </h1>
    </div>
    <div class="middle-input-div col-lg-3 col-sm-12">
      <label class="middle-label">TIMEZONE</label>
      <h1 class="middle-input">{{ ipData.location.timezone }}</h1>
    </div>
    <div class="middle-input-div col-lg-3 col-sm-12">
      <label class="middle-label">ISP</label>
      <h1 class="middle-input r-line">{{ ipData.isp }}</h1>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    ipData: {
      default: {
        ip: "",
        location: {
          country: "",
          region: "",
          timezone: "",
        },
        isp: "",
      },
    },
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Rubik:wght@400;500;700&display=swap");

.middle-input {
  height: 45px;
  font-size: 30px;
  font-weight: 500;
  font-family: Rubik, sans-serif;
  margin-bottom: 10%;
  border-right: 0.5px solid hsl(0deg 0% 59%);
}

.middle-input-div {
  padding: 2%;
}

.middle-label {
  color: hsl(0deg 0% 59%);
  letter-spacing: 1px;
  font-size: 12px;
  font-weight: 700;
  font-family: Rubik, sans-serif;
}

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

.r-line {
  border-style: none;
}
</style>
