<template>
  <div class="ip-info-card">
    <p>{{ title }}</p>
    <h3 class="text">{{ value }}</h3>
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
  margin: 1.8em;
  text-transform: uppercase;
  border-right-style: inset;
  color: grey;
}

.text {
  font-weight: 700;
  size: 5px;
  color: black;
  opacity: 0.8;
}
</style>
