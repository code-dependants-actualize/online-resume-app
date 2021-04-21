<template>
  <div id="show-resume">
    <!-- Header -->
    <h1>{{ resumeInfo.first_name }} {{ resumeInfo.last_name }}</h1>
    <h3>{{ resumeInfo.email }} | {{ resumeInfo.phone }}</h3>
    <!-- Links -->
    <p>{{ resumeInfo.twitter_handle }} | {{ resumeInfo.website_url }} | {{ resumeInfo.linkedin_url }} | {{ resumeInfo.github_url }}</p>
    <!-- Short Bio -->
    <p>{{ resumeInfo.bio }}</p>
    <!-- Expierence -->
    <h3>Exeprience</h3>
    <div id="experiences" v-for="experience in resumeInfo.experiences" v-bind:key="experience.id">
      <p>
        <strong>{{ experience.company_name }}: {{experience.job_title }}</strong>
        {{ experience.start_date }}-{{ experience.end_date }}
      </p>
      <p>{{ experience.details }}</p>
    </div>
    <!-- Education -->
    <h3>Education</h3>
    <div id="education" v-for="education in resumeInfo.educations" v-bind:key="education.id">
      <p>{{ education.university}} {{ education.degree }}: {{ education.start_date }}-{{ education.end_date }}</p>
      <p>{{ education.ed_details }}</p>
    </div>
    <!-- Skills -->
    <h3>Skills</h3>
    <div id="skills" v-for="skill in resumeInfo.skills" v-bind:key="skill.id">
      <p>{{ skill.name }}</p>
    </div>
    <!-- Capstone -->
    <h3>Capstone</h3>
    <div id="capstone" v-for="capstone in resumeInfo.capstones" v-bind:key="capstone.id">
      <h6>{{ capstone.name }}</h6>
      <p>{{ capstone.description }}</p>
      <p>@{{ capstone.url }}</p>
      <img src="" />
      <!-- this is optional-->
    </div>
    <a class="twitter-timeline" href="https://twitter.com/big_ben_clock?ref_src=twsrc%5Etfw">Tweets by big_ben_clock</a>
  </div>
</template>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
<style></style>

<script>
import axios from "axios";
// import { Tweet, Moment, Timeline } from "vue-tweet-embed";
export default {
  data: function () {
    return {
      resumeInfo: {},
      // first_name: "First Name",
      // last_name: "Last Name",
      // email: "email.com",
      // phone_number: "555-555-5555",
      // twitter_handle: "handle@twitter",
      // online_resume_irl: "resume.com",
      // personal_url: "blog.com",
      // linkedin_url: "linkedin.com",
      // github_url: "github.com",
      // short_bio: "this a short bio about me, a resume user!",
      // company_name: "Company",
      // job_title: "Job title",
      // start_date: "Start date",
      // end_date: "End date",
      // job_details: "These are these details of a job I did. Go me!",
      // university_name: "University",
      // degree: "degree",
      // ed_start_date: "Start date",
      // ed_end_date: "End date",
      // ed_details: "These are details about education",
      // skill_name: "skill",
      // capstone_name: "Capstone",
      // capstone_description: "This is the description of my capstone",
      // capstone_url: "capstone.com",
    };
  },
  created: function () {
    this.showResume();
  },
  methods: {
    showResume: function () {
      axios.get("/api/students/" + this.$route.params.id).then((response) => {
        console.log(response.data);
        this.resumeInfo = response.data;
      });
    },
  },
};
</script>
