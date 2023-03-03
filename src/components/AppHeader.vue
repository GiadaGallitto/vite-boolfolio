<script>
export default {
    name: 'AppHeader'
}
</script>

<template>
    <header>
        <nav class="navbar navbar-expand-md navbar-light bg-light">
            <div class="container">
                <a class="navbar-brand fs-3" href="#">My Portfolio</a>
                <button class="navbar-toggler" type="button" data-bs-toggle="collapse"
                    data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false"
                    aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>
                <div class="collapse navbar-collapse" id="navbarSupportedContent">
                    <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                        <li class="nav-item me-2" :class="this.$route.name === 'home' ? 'active' : ''">
                            <router-link class="nav-link" :to="{ name: 'home'}" >
                                Home
                            </router-link>
                        </li>
                        <li class="nav-item me-2" :class="this.$route.name === 'projects' ? 'active' : ''">
                            <router-link class="nav-link" :to="{ name: 'projects'}" >
                                Projects
                            </router-link>
                        </li>
                        <li class="nav-item me-2" :class="this.$route.name === 'about-us' ? 'active' : ''">
                            <router-link class="nav-link" :to="{ name: 'about-us'}" >
                                About Us
                            </router-link>
                        </li>
                    </ul>
                    <form class="d-flex">
                        <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
                        <button class="btn btn-outline-success" type="submit">Search</button>
                    </form>
                </div>
            </div>
        </nav>
    </header>
</template>

<style lang="scss"></style>