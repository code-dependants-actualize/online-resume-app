<template>
  <<<<<<< HEAD
  <div id="show-resume">
    <!-- Header -->
    <h1>{{ first_name }} {{ last_name }}</h1>
    <h3>{{ email }} | {{ phone_number }}</h3>
    <!-- Links -->
    <p>{{ twitter_handle }} | {{ online_resume_url }} | {{ personal_url }} | {{ linkedin_url }} | {{ github_url }}</p>
    <!-- Short Bio -->
    <p>{{ shot_bio }}</p>
    <!-- Expierence -->
    <h3>Expierence</h3>
    <div id="expierene">
      <p>
        <strong>{{ company_name }}: {{ job_title }}</strong>
        {{ start_date }}-{{ end_date }}
      </p>
      <p>{{ job_details }}</p>
    </div>
    <!-- Education -->
    <h3>Education</h3>
    <div id="education">
      <p>{{ university_name }} {{ degree }}: {{ ed_start_date }}-{{ ed_end_date }}</p>
      <p>{{ ed_details }}</p>
    </div>
    <!-- Skills -->
    <h3>Skills</h3>
    <div id="skills">
      <p>{{ skill_name }}</p>
    </div>
    <!-- Capstone -->
    <h3>Capstone</h3>
    <div id="capstone">
      <p>{{ capstone_name }}</p>
      <p>{{ capstone_description }}</p>
      <p>{{ capstone_url }}</p>
      <img src="" />
      <!-- this is optional-->
    </div>
  </div>
</template>

<style></style>

<script>
import axios from "axios";
export default {
  data: function () {
    return {
      resumeInfo: {},
      first_name: "First Name",
      last_name: "Last Name",
      email: "email.com",
      phone_number: "555-555-5555",
      twitter_handle: "handle@twitter",
      online_resume_irl: "resume.com",
      personal_url: "blog.com",
      linkedin_url: "linkedin.com",
      github_url: "github.com",
      short_bio: "this a short bio about me, a resume user!",
      company_name: "Company",
      job_title: "Job title",
      start_date: "Start date",
      end_date: "End date",
      job_details: "These are these details of a job I did. Go me!",
      university_name: "University",
      degree: "degree",
      ed_start_date: "Start date",
      ed_end_date: "End date",
      ed_details: "These are details about education",
      skill_name: "skill",
      capstone_name: "Capstone",
      capstone_description: "This is the description of my capstone",
      capstone_url: "capstone.com",
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
