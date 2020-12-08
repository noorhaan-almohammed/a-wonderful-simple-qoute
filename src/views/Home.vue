<template>
  <div class="container">
    <app-header :qouteCount="qoutes.length" :maxQoutes="maxQoute"></app-header>
    <app-new-qoute @qouteAdded="newQoute"></app-new-qoute>
    <app-qoute-grid
      :qoutes="qoutes"
      @qouteDeleted="deleteQoute"
    ></app-qoute-grid>

    <div class="row" v-if="qoutes.length == 0">
      <div class="col-sm-12 text-center">
        <div class="empty alert alert-info">
          &#x1F4D4; ^ Type some Qoute ^ &#x1F4D4;
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">
          &#x1F449; Info : click on Qoute to delete it .
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import QouteGrid from "../components/QouteGrid.vue";
import NewQoute from "../components/newQoute.vue";
import Header from "../components/Header.vue";
export default {
  data: function() {
    return { qoutes: ["just a qoutte to see something"], maxQoute: 10 };
  },
  methods: {
    newQoute(qoute) {
      if (this.qoutes.length >= this.maxQoute) {
        return alert("please delete some qoutes first");
      }
      this.qoutes.push(qoute);
    },
    deleteQoute(index) {
      this.qoutes.splice(index, 1);
      if (this.qoutes.length == 0) {
        return;
      }
    }
  },
  components: {
    appQouteGrid: QouteGrid,
    appNewQoute: NewQoute,
    appHeader: Header
  }
};
</script>

<style>
.container {
  padding: 3%;
  margin-left: 7%;
  margin-right: 2%;
  margin-top: 3%;
  border: 5px solid #f382f2;
  border-image: linear-gradient(
      0deg,
      rgb(192, 42, 185) 0%,
      rgb(212, 90, 192) 27%,
      rgb(245, 185, 227) 100%
    )
    1;
  background: radial-gradient(#f382f2, transparent),
    url(../assets/img.jpg) center/cover;
}
.alert-info {
  color: #f5f10b;
  background-color: #ddda1448;
  border-color: #e5ee91;
}
.empty {
  color: #88ecf1;
  background-color: #9eeae248;
  border-color: #3ae5ef;
}
body {
  background-image: radial-gradient(#e9ef08, rgb(249 221 248));
}
</style>
