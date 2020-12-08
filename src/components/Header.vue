<template>
  <div class="row">
    <div class="col-sm-12">
      <h3>&#x1F31E; Qoute Added</h3>
      <div class="progress">
        <div
          class="progress-bar"
          role="progressbar"
          aria-valuenow="60"
          aria-valuemin="100"
          :style="{ width: (qouteCount / maxQoutes) * 100 + '%' }"
        >
          {{ qouteCount }} / {{ maxQoutes }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["qouteCount", "maxQoutes"]
};
</script>

<style scoped>
.progress-bar {
  background: radial-gradient(#f382f2, transparent);
}
h3 {
  color: rgb(243, 208, 238);
  font-size: 25px;
  font-family: Georgia, "Times New Roman", Times, serif;
}
</style>
