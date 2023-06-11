<template>
    <div class = "detail-project">
    
        <div class = "detail-project-image-container">
          <img src= "https://picsum.photos/536/354" class="detail-project__image">
        </div>
        <div class = "detail-project-information">
          <h2>This is my project</h2>
          <p>The description of my project to be presented in the main page.</p>
        </div>
      
    </div>
  </template>
  
  <script>
  export default {
    name: "ProjectDetail",
    data() {
        return {
        ProjectInfo: [] 
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
    display: flex;
    gap: 25px;
  }
  .detail-project-image-container{
    height: 400px;
    display: flex;
  }
  .detail-project__image{
    width: 100%;
    aspect-ratio: 1;
    object-fit: cover;
  }
  .detail-project-information{
    display: block;
  }
  .detail-project-information > h2,p{
    text-transform: uppercase;
  }
  .detail-project-information > h2{
    letter-spacing: 1px;
    word-spacing: 3px;
    background-color: pink;
    padding: 8px 15px;
    margin: 0px;
    width: 59%;
    text-align: left;
  }
  </style>
  