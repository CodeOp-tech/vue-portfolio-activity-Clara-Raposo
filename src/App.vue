<template>
  <div>
    <h1>MY PORTFOLIO</h1>
    <div :class="{'div-buttons': true}">
      <button @click="isAdmin = true" :class="{'admin-button': true, 'selected-button':isAdmin}">ADMIN</button>
      <button @click="isAdmin = false" :class="{'user-button': true, 'selected-button':!isAdmin}">USER</button>
    </div>
    <admin-view v-if="isAdmin" @createProject="addProject" />
    <user-view v-else :projects="allProjects"/>
  </div>
</template>

<script>
import AdminView from "./components/AdminView.vue"; //importa archivos
import UserView from "./components/UserView.vue";
import Project1 from "./images/project1.jpg"
import Project2 from "./images/project2.jpg"
import Project3 from "./images/project3.jpg"

export default {
  name: "app",
  components: {    //referencia los archivos importados
    userView: UserView,
    adminView: AdminView,
  },
  data() {
    return {
      isAdmin: true, //verifica si estás dentro de la pestaña de Admin
      allProjects: [
        {
        title: "distopía presente",
        image: Project1,
        description: "my description",
        },
        {
        title: "la luz tenue de dios",
        image: Project2,
        description: "my description 2",
        },
        {
        title: "masones preparados para el apocalipsis",
        image: Project3,
        description: "my description 3",
        }
      ], //array donde se guardan los proyectos
    };
  },
  methods: {
    addProject(project) {
      this.allProjects.push(project);
    },
  }
};
</script>

<style>
body{
  background-color: pink;
  font-family:arial;
  text-align: center;
  margin: 0px;
  padding: 0px;
}

h1{
  letter-spacing: 2px;
  word-spacing: 4px;
  padding: 15px;
  padding-right: 80px;
  margin: 0px;
  margin-top: 30px;
  margin-bottom: 20px;
  font-family: helvetica;
  text-align: right;
  width: 500px;
  background-color: ivory;
}

.div-buttons{
  width: 100%;
  position: absolute;
  top: 0px;
}

.admin-button{
  width: 80px;
  display: inline-block;
  border: none;
  background-color: transparent;
  margin: 10px;
  margin-right: 3px;
  cursor: pointer;
}

.user-button{
  width: 80px;
  display: inline-block;
  border: none;
  background-color: transparent;
  margin: 10px;
  cursor: pointer;
 }

.selected-button{
  background-color: ivory;
}
</style>
