<template>
  <div class="home">
    Home
    <div v-if="projects.length">
      <div v-for="project in projects" :key="project.id">
        <h3>{{ project.title }}</h3>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  components: {},
  data() {
    return {
      projects: [],
    };
  },
  mounted() {
    fetch("http://localhost:3000/projects")
      .then((resp) => resp.json())
      .then((data) => (this.projects = data))
      .catch((err) => console.log(err));
  },
};
</script>
