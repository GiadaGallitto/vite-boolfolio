<script>
import axios from 'axios';
import SingleProject from '../pages/SingleProject.vue';

export default {
    name: 'AppMain',
    data() {
        return {
            projects: [],
        }
    },

    props: {
        author: String,
        slug: String,
        type: String,
        image: String,
        technologies: Array,
        title: String,
        description: String,
        start_date: Number,
    },
}
</script>

<template>
    <div class="card">
        <div class="card-header d-flex align-items-center justify-content-center mb-2">
            <span>
                <strong>Author: </strong>{{ author }}
            </span>
        </div>

        <div class="d-flex justify-content-between mb-1">
            <div class="type">
                <p>
                    <strong>Type: </strong>{{ type.name }}
                </p>
            </div>
            <div class="technologies">
                <strong>Technology: </strong>
                <span class="technology me-2" v-for="technology in technologies">
                    {{ technology.name }}
                </span>
            </div>
        </div>

        <h5 class="card-title">{{ title }}</h5>
        <img :src="image" class="img-fluid" alt="project-image">
        <div class="card-body">
            <p class="card-text">{{ description }}</p>
            <router-link class="btn btn-primary" :to="{name: 'project', params:{ slug: slug }}" >
                Read more...
            </router-link>
        </div>
        <div class="card-footer text-muted">
            <span><strong>Start date: </strong>{{ start_date }}</span>
        </div>
    </div>
</template>

<style lang="scss" scoped></style>