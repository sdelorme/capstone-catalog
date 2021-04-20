<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <div v-for="student in students" v-bind:key="student.id">
      Name: {{ student.first_name }} {{ student.last_name }}
      <br />
      Capstones: {{ student.capstones }}
      <hr />
    </div>
  </div>
</template>

<style></style>

<script>
import axios from "axios";
export default {
  data: function () {
    return {
      message: "Team Ben, Seth, Thom",
      students: [],
      capstones: [],
    };
  },
  created: function () {
    this.capstoneIndex();
    this.studentIndex();
  },
  methods: {
    capstoneIndex: function () {
      axios.get("/api/capstones").then((response) => {
        console.log(response.data);
        this.capstones = response.data;
      });
    },
    studentIndex: function () {
      axios.get("/api/students").then((response) => {
        this.students = response.data;
      });
    },
  },
};
</script>
