<template>
  <div class="row">
    <app-qoute
      v-for="(qoute, index) in qoutes"
      :key="index"
      @click="deleteQoute(index)"
    >
      {{ qoute }}
    </app-qoute>
  </div>
</template>
<script>
// @click.native="deleteQoute(index)"
import Qoute from "./qoute.vue";
export default {
  props: ["qoutes"],
  components: {
    appQoute: Qoute
  },
  methods: {
    deleteQoute(index) {
      this.$emit("qouteDeleted", index);
    }
  }
};
</script>
<style scoped></style>
