<script>
import axios from 'axios';

export default {
  name: 'AppMain',
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

    <div class="row justify-content-between g-4">
      <div class="col-6 project" v-for="project in projects">
        <div class="card">
          <div class="card-header d-flex align-items-center justify-content-center mb-2">
            <span>
              <strong>Author: </strong>{{ project.author }}
            </span>
          </div>

          <div class="d-flex justify-content-between mb-1">
            <div class="type">
              <p>
                <strong>Type: </strong>{{ project.type.name }}
              </p>
            </div>
            <div class="technologies">
              <strong>Technology: </strong>
              <span class="technology me-2" v-for="technology in project.technologies">
                  {{ technology.name }}
              </span>
            </div>
          </div>

          <h5 class="card-title">{{ project.title }}</h5>
          <img :src="project.image" class="img-fluid" alt="project-image">
          <div class="card-body">
            <p class="card-text">{{ project.description }}</p>
            <a href="#" class="btn btn-primary">Read more...</a>
          </div>
          <div class="card-footer text-muted">
            <span><strong>Start date: </strong>{{ project.start_date }}</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped></style>
