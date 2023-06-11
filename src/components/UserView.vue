<template>
  <project-detail/>
  <div v-if="projects.length > 0" class = "grid-container" @click="handleProject">
    <article v-for="project in projects" :key="project.title" :project="project">
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

  methods: {
    handleProject(){
      this.$emit("highlightProject",{
        title: this.title,
        image: this.image,
        description: this.description,
      })
    }
  },
};
</script>

<style>
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
}
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
