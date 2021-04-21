<template>
  <div class="home">
    <div class="container">
      <div class="row row-cols-1 row-cols-md-4">
        <div v-for="resume in resumes" v-bind:key="resume.id">
          <div class="col mb-4">
            <!-- V-for loop to load resume index -->
            <div class="card">
              <img
                src=""
                class="card-img-top"
                alt=""
              />
              <div class="card-body">
                <h5 class="card-title">{{ resume.first_name }} {{ resume.last_name }}</h5>
                <p class="card-text">Web Developer</p>
              </div>
              <ul class="list-group list-group-flush">
                <li class="list-group-item">{{ resume.bio }}</li>
              </ul>
              <div class="card-body">
                <router-link v-bind:to="`/student_resumes/${resume.id}`" class="card-link">Full resume</router-link>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style></style>

<script>
import axios from "axios";

export default {
  data: function () {
    return {
      resumes: [],
    };
  },
  created: function () {
    this.indexResume();
  },
  methods: {
    indexResume: function () {
      axios.get("/api/students").then((response) => {
        console.log(response);
        this.resumes = response.data;
      });
    },
  },
};
</script>
