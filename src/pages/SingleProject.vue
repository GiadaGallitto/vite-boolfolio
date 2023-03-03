<script>
import ProjectCard from '../components/ProjectCard.vue';
import axios from 'axios';

export default {
    components: {
        ProjectCard,
    },

    data() {
        return {
            project: null,
        }
    },

    methods: {
        getProject() {
            axios.get(`http://127.0.0.1:8000/api/projects/${this.$route.params.slug}`, {
                params: {

                }
            })
                .then((response) => {
                    this.project = (response.data.results);
                })
                .catch(function (error) {
                    console.warn(error);
                });
        }
    },

    created() {
        this.getProject();
    },
}
</script>

<template>
    <div class="row">
        <ProjectCard :project="project" :isShow="true" />
    </div>
</template>

<style lang="scss"></style>