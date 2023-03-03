<script>
import ProjectCard from "./ProjectCard.vue";
import axios from 'axios';

export default {
  name: 'AppMain',
  components: {
    ProjectCard,
  },

  data() {
    return {
      projects: [],
      apiUrl: 'http://127.0.0.1:8000/api/projects',
    }
  },

  methods: {
    getProjects() {
      axios.get(this.apiUrl, {
        params: {

        }
      })
        .then((response) => {
          this.projects = (response.data.results.data);
        })
        .catch(function (error) {
          console.warn(error);
        });
    }
  },

  created() {
    this.getProjects();
  },
}
</script>

<template>
  <section class="container">
    <div class="row mb-3">
      <div class="col-12">
        <h1>My Portfolio</h1>
      </div>
    </div>

    <div class="row justify-content-around g-4">
      <ProjectCard class="col-5 text-center" v-for="project in projects" 
      :author="project.author"
      :type="project.type"
      :technologies="project.technologies"
      :title="project.title"
      :image="project.image"
      :description="project.description"
      :start_date="project.start_date"
      />
    </div>
  </section>
</template>

<style lang="scss" scoped></style>
