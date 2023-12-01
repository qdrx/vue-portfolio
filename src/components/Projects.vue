<template>
  <div class="projects-container">
    <div class="projects">
      <div v-for="(project, index) in projects" :key="index" class="project">
        <h3>{{ project.name }}</h3>
        <p>{{ project.description }}</p>
        <div class="details">
          <span v-if="project.language">{{ project.language }}</span>
          <a v-if="project.url" :href="project.url" target="_blank">View on GitHub</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'GitHubProjects',
  data() {
    return {
      projects: [
        {
          name: 'E-commerse Example',
          description: 'Written in NestJS with PostgreSQL, Redis, Docker.',
          language: 'TypeScript',
          url: 'https://github.com/qdrx/ecom-example'
        },
        {
          name: 'Book AI',
          description: 'NestJS application with OpenAI and OpenLibrary integration.',
          language: 'TypeScript',
          url: 'https://github.com/qdrx/book-ai'
        },
      ]
    };
  }
};
</script>

<style scoped>
.projects-container {
  margin-top: 50px;
  margin-bottom: 50px;
  display: flex;
  justify-content: center;
}

.projects {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 20px;
  max-width: 1200px;
}

.project {
  width: 300px;
  border: 1px solid #ff79c6;
  border-radius: 6px;
  padding: 20px;
  box-sizing: border-box;
}

.project h3 {
  font-size: 18px;
  margin-bottom: 10px;
}

.project p {
  font-size: 14px;
  color: #586069;
  margin-bottom: 10px;
}

.project .details {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 14px;
}

.project .details span {
  color: #0366d6;
}

.project .details a {
  color: #0366d6;
  text-decoration: none;
}

@media screen and (max-width: 600px) {
  .project {
    width: calc(100% - 40px);
  }
}
</style>