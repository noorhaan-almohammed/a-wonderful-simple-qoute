<template>
  <div class="col-sm-6 col-md-4 col-lg-3">
    <div class="panel panel-default">
      <div class="panel-body qoute">
        <slot></slot>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["qoutes"]
};
</script>
<style scoped>
.panel-body {
  font-family: "Arizonia", cursive;
  font-size: 24px;
  color: #6e6e6e;
  background: radial-gradient(#f88ee1, transparent);
  color: rgb(121, 45, 117);
  text-align: center;
  border: 1px solid rgb(241, 120, 211);
  overflow: overlay;
}
.qoute {
  cursor: pointer;
}
.qoute:hover {
  background-color: #ffe2e2;
}
</style>
