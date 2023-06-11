<template>
    <div class = "detail-project">
      <article v-for="project in projects" :key="project.title" :project="project">
        <img :src= "project.image" :alt="project.title" class="grid-container__image">
        <h2>{{ project.title }}</h2>
        <p>{{ project.description }}</p>
      </article>
    </div>
  </template>
  
  <script>
  export default {
    name: "ProjectDetail",
    data() {
        return {
        isAdmin: true, //verifica si estás dentro de la pestaña de Admin
        allProjects: [] //array donde se guardan los proyectos
        };
    },
    methods: {
        addProject(project) {
        this.allProjects.push(project);
        }

    }
  };
  </script>
  
  <style>
  .detail-project{
    width: 85%;
    background-color: ivory;
    padding: 20px;
    float: right;
    margin-bottom: 20px;
  }
  
  </style>
  