<template>
  <div class="home">
    <div class="container">
      <div class="row row-cols-1 row-cols-md-4">
        <div v-for="resume in resumes" v-bind:key="resume.id">
          <div class="col mb-4">
            <!-- V-for loop to load resume index -->
            <div class="card">
              <img
                src="https://lh3.googleusercontent.com/ogw/ADGmqu_0kyTr1Xovz5G5SGSTsaizg6EEEyDG3TzL2ebQuw=s64-c-mo"
                class="card-img-top"
                alt=""
              />
              <div class="card-body">
                <h5 class="card-title">{{ resume.name }}</h5>
                <p class="card-text">{{ resume.title }}</p>
              </div>
              <ul class="list-group list-group-flush">
                <li class="list-group-item">{{ resume.bio }}</li>
              </ul>
              <div class="card-body">
                <a href="#" class="card-link">Full resume</a>
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
      resumes: [
        { name: "First Last", title: "Web developer", bio: "A short bio" },
        { name: "First Last", title: "Web developer", bio: "A short bio" },
        { name: "First Last", title: "Web developer", bio: "A short bio" },
        { name: "First Last", title: "Web developer", bio: "A short bio" },
        { name: "First Last", title: "Web developer", bio: "A short bio" },
        { name: "First Last", title: "Web developer", bio: "A short bio" },
        { name: "First Last", title: "Web developer", bio: "A short bio" },
        { name: "First Last", title: "Web developer", bio: "A short bio" },
        { name: "First Last", title: "Web developer", bio: "A short bio" },
        { name: "First Last", title: "Web developer", bio: "A short bio" },
        { name: "First Last", title: "Web developer", bio: "A short bio" },
        { name: "First Last", title: "Web developer", bio: "A short bio" },
      ],
    };
  },
  created: function () {
    this.indexResume();
  },
  methods: {
    indexResume: function () {
      axios.get("/api/students").then((response) => {
        console.log(response);
      });
    },
  },
};
</script>
