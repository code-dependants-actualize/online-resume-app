<template>
  <div class="home">
    <h1>{{ resumeInfo }}</h1>
  </div>
</template>

<style></style>

<script>
import axios from "axios";
export default {
  data: function () {
    return {
      resumeInfo: {},
    };
  },
  created: function () {
    this.showResume();
  },
  methods: {
    showResume: function () {
      axios.get("/api/students/" + this.$route.params.id).then((response) => {
        this.resumeInfo = response.data;
      });
    },
  },
};
</script>
