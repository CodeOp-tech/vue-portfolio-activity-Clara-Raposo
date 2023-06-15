<template>
  <project-detail @select="selectProject" :project="featuredProject" />
  <div v-if="projects.length > 0" class = "grid-container" >

    <article v-for="project in projects" :key="project.title" :project="project" @click="handleClick(project)"><!--key es un elemento necesario en todos los v-for//  :project="project"-->
      <img :src= "project.image" :alt="project.title" class="grid-container__image">
    </article>
  </div>
  <div v-else>
    <h2>ADD A PROJECT TO YOUR PORTFOLIO</h2>
  </div>
  <!--<div class="user-view">User View</div>-->
</template>

<script>
import ProjectDetail from "./ProjectDetail.vue";

export default {
  name: "UserView",
  components: {    //referencia los archivos importados
    projectDetail: ProjectDetail,
  },
  props: ["projects"],

  data(){
    return{
      featuredProject: this.projects[0],
    }
  },

  methods: {
    handleClick(project){
      this.featuredProject = project
    }
  },

};
</script>

<style>
h2{
  letter-spacing: 1px;
  word-spacing: 4px;
}
.grid-container{
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  width: 85%;
  background-color: ivory;
  gap: 8px;
  padding: 20px;
  float: left;
  margin-bottom: 20px;
}
.grid-container__image{
  aspect-ratio: 1;
  width: 100%;
  object-fit: cover;
  cursor: pointer;
}
/*.grid-container__image:hover{
  width: 150%
}*/
.user-view{
  text-align:center;
  text-transform: uppercase;
  font-family: arial;
  margin: 15px;
  display: block;
  width: 150px;
  float: right;
  position: relative;
  left: -43%;
}

</style>
