<script>
import axios from 'axios';

export default {
    name: 'AppMain',
    data() {
        return {
            projects: [],
        }
    },

    props: {
        // author: String,
        // slug: String,
        // type: String,
        // image: String,
        // technologies: Array,
        // title: String,
        // description: String,
        // start_date: Number,
        'project': {
            type: Object,
            required: true,
        },

        'isShow':{
            type: Boolean,
            required: false,
            default: false,
        }
    },
}
</script>

<template>
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
            <router-link v-if="!isShow" class="btn btn-primary" :to="{name: 'project', params:{ slug: project.slug }}" >
                Read more...
            </router-link>
        </div>
        <div class="card-footer text-muted">
            <span><strong>Start date: </strong>{{ project.start_date }}</span>
        </div>
    </div>
</template>

<style lang="scss" scoped></style>