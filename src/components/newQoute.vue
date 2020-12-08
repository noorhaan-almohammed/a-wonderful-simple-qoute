<template>
  <div class="row">
    <form>
      <div
        class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group"
      >
        <label> &#x1F342; Qoute &#x1F342;</label>
        <textarea
          placeholder="type your qoute "
          class="form-control"
          rows="3"
          v-model="qoute"
        ></textarea>
      </div>
      <div
        class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group"
      >
        <button class="btn btn-primary" @click.prevent="createQoute">
          Add qoute
        </button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      qoute: ""
    };
  },
  methods: {
    createQoute() {
      this.$emit("qouteAdded", this.qoute);
      this.qoute = "";
    }
  }
};
</script>

<style scoped>
textarea {
  color: rgb(31 5 243);
  border: 4px solid rgb(250, 214, 242);
  background: radial-gradient(#f382f2, transparent);
}
textarea::-webkit-input-placeholder {
  color: rgb(146, 240, 38) !important;
}

textarea:-moz-placeholder {
  /* Firefox 18- */
  color: rgb(146, 240, 38) !important;
}

textarea::-moz-placeholder {
  /* Firefox 19+ */
  color: rgb(146, 240, 38) !important;
}

textarea:-ms-input-placeholder {
  color: rgb(146, 240, 38) !important;
}
.form-control:focus {
  border-color: #e966c0;
}
.btn {
  background: radial-gradient(#b416b2, transparent);
  border-radius: 15px;
  border-color: #b416b2;
  color: rgb(240, 214, 236);
}
.row {
  text-align: center;
}
label {
  color: rgb(243, 208, 238);
  font-size: 25px;
  font-family: Georgia, "Times New Roman", Times, serif;
}
</style>
