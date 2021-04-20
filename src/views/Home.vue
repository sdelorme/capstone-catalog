<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <div v-for="student in students" v-bind:key="student.id">{{ student.first_name }} {{ student.last_name }}</div>
  </div>
</template>

<style></style>

<script>
import axios from "axios";
export default {
  data: function () {
    return {
      message: "Team Ben, Seth, Thom",
      students: [
        {
          first_name: "Maya",
          last_name: "Angelou",
        },
        {
          first_name: "Spin",
          last_name: "Drift",
        },
      ],
      capstones: [
        {
          name: "Icy Hot",
          description: "First it's icy, then it's hot.",
          url: "https://images-na.ssl-images-amazon.com/images/I/71t2faI0HjL._AC_SL1500_.jpg",
        },
      ],
    };
  },
  created: function () {},
  methods: {
    capstoneIndex: function () {
      axios.get("./api/capstones").then((response) => {
        this.capstones = response.data;
      });
    },
    studentIndex: function () {
      axios.get("./api/students").then((response) => {
        this.students = response.data;
      });
    },
  },
};
</script>
