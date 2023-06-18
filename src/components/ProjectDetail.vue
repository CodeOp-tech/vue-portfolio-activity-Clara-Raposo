<template>
  <section>
    <div class = "detail-project">
    
        <div class = "detail-project-image-container">
          <img :src= "project.image" :alt="project.title" class="detail-project__image">
        </div>
        <div class = "detail-project-information">
          <h2>{{ project.title }}</h2>
          <p>{{ project.description }}</p>
        </div>
      
    </div>
  </section>
</template>
  
  <script>
  export default {
    name: "ProjectDetail",
    props:['project'],
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
    text-align: left;
  }
  .detail-project-information > h2{
    letter-spacing: 1px;
    word-spacing: 3px;
    background-color: pink;
    padding: 8px 15px;
    margin: 0px;
    width: 320px;
    text-align: left;
  }
  .detail-project-information > p{
    width: 700px;
    line-height: 25px;
    word-spacing: 4px;
    letter-spacing: 1px;
  }
  </style>
  