<template>
  <div class="home">
    <h1>{{ currentCapstone.student }}'s {{ message }}</h1>
    <p>name: {{ currentCapstone.name }}</p>
    <p>description: {{ currentCapstone.description }}</p>
    <p>url: {{ currentCapstone.url }}</p>
    <p>screenshot: {{ currentCapstone.screenshot }}</p>
    <p>student: {{ currentCapstone.student }}</p>
  </div>
</template>

<style></style>

<script>
import axios from "axios";
export default {
  data: function () {
    return {
      message: "Capstone",
      currentCapstone: {},
    };
  },
  created: function () {
    axios.get("/api/capstones/" + this.$route.params.id).then((response) => {
      console.log(response.data);
      this.currentCapstone = response.data;
    });
  },
  methods: {},
};
</script>
