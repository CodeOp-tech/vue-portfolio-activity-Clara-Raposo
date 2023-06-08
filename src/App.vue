<template>
  <div>
    <h1>MY PORTFOLIO</h1>
    <button @click="isAdmin = true" class="admin-button">ADMIN</button>
    <button @click="isAdmin = false" class="user-button">USER</button>
    <admin-view v-if="isAdmin" @createProject="addProject" />
    <user-view v-else />
  </div>
</template>

<script>
import AdminView from "./components/AdminView.vue";
import UserView from "./components/UserView.vue";

export default {
  name: "app",
  components: {
    userView: UserView,
    adminView: AdminView
  },
  data() {
    return {
      isAdmin: true,
      allProjects: []
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
body{
  background-color: pink;
  font-family:arial;
  text-align: center;
}

h1{
  letter-spacing: 2px;
  word-spacing: 4px;
  padding: 15px;
  margin: 0px;
  margin-top: 30px;
  font-family: helvetica;
}

.admin-button{
  width: 80px;
  position: absolute;
  top: 0px; 
  left: 44%;
  border: none;
  border-right: solid 1px black;
  background-color: transparent;
  margin: 10px;
  margin-right: 3px;
}

.user-button{
  width: 80px;
  position: absolute; 
  top: 0px;
  left: 50%;
  border: none;
  background-color: transparent;
  margin: 10px;
  margin-left: -10px;
}
</style>
