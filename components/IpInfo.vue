<template>
  <div class="ip-info-card">
    <p>{{ title }}</p>
    <h1>{{ value }}</h1>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    value: {
      type: String,
      required: true,
    },
  },
};
</script>

<style>
.ip-info-card {
  flex: 1;
  padding-top: 1em;
  margin: 1em;
}
</style>
