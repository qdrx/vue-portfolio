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
          name: 'Project 1',
          description: 'Description of Project 1',
          language: 'JavaScript',
          url: 'https://github.com/username/project-1'
        },
        {
          name: 'Project 2',
          description: 'Description of Project 2',
          language: 'Python',
          url: 'https://github.com/username/project-2'
        },
        // Add more projects as needed
      ]
    };
  }
};
</script>

<style scoped>
.projects-container {
  display: flex;
  justify-content: center;
}

.projects {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 20px;
  max-width: 1200px; /* Опционально: устанавливаем максимальную ширину */
}

.project {
  width: 300px; /* Опционально: задаем ширину проекта */
  border: 1px solid #e1e4e8;
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
    width: calc(100% - 40px); /* Опционально: на узких экранах ширина 100% минус отступы */
  }
}
</style>