<template>
  <router-link :to="{name: 'ProjectDetailsPage', params: {id: project.id}}" class="projectComponent row highlighted-project bg-dark no-gutters mb-4">
    <div class="col-5 p-4">
      <div class="row flex-column h-100">
        <div class="col-auto mb-2 project-type">
          <small>{{ project.type }}</small>
        </div>
        <div class="col-auto project-title">
          <h3>{{ project.projectName }}</h3>
        </div>
        <div class="col-auto project-description mb-3">
          {{ project.shortDescription }}
        </div>
        <div class="col-auto mt-auto project-link">
          <router-link :to="{name: 'ProjectDetailsPage', params: {id: project.id}}">
            View Project ->
          </router-link>
        </div>
      </div>
    </div>
    <div class="col">
      <div class="highlighted-project-hero" :style="`background-image: url('${project.heroImage}');`">
      </div>
    </div>
  </router-link>
</template>

<script>
import { Project } from '../models/projectModel.js'
export default {
  name: 'ProjectComponent',
  props: { project: { type: Project, default: () => new Project() } }
}
</script>

<style lang="scss" scoped>
.highlighted-project-hero {
  background-position: center;
}
.projectComponent {
  box-shadow: rgba(0, 0, 0, 0.15) 2px 2px 0.5em;
}
.projectComponent:hover {
  color: #fff;
  text-decoration: none;
  box-shadow: rgba(0, 0, 0, 0.5) 5px 5px 0.5em;
}
</style>
