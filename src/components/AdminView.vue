<template>
  
  <div class = "form-container">
    <div class = "form-h2"><h2>ADD NEW PROJECT</h2></div>
    <form class ="form" @submit.prevent="handleSubmit">
      <div class="form-container-title-image">
        <label class ="form__project-title">
          TITLE
          <br>
          <input v-model="title" type = "text" id="project-title" name="title"/>
        </label>
        <label class ="form__project-image">
          IMAGE
          <br>
          <input v-model="image" type="url" id="project-image" name="image"/>
        </label>
      </div>
      <label class="form__project-description">
        DESCRIPTION
        <br>
        <textarea v-model="description" id="project-description" name="description"></textarea>
      </label>
      <button class="button-submit">SUBMIT</button>
    </form>
  </div>
</template>

<script>
import { resetTracking } from '@vue/reactivity';

export default {
  name: "AdminView",
  data() { //información que recoge el formulario dentro de la página. Siempre devuleve un objeto 
    return {
      title: "",
      image: "",
      description: "",
    };
  },
  methods: {      //eventos dentro de la página que transforman la propia página
    handleSubmit() {
      this.$emit("createProject", {
        title: this.title,
        image: this.image,
        description: this.description,
      })
      this.reset()
    },

    reset(){
      this.image = "";
      this.title = "";
      this.description = "";
    }
  }
};
</script>

<style>
.form-container{
  width: 80%;
  height: 285px;
  background-color: ivory;
  padding: 5px;
  padding-left: 15%;
  padding-right: 0;
  text-align: right;

}
.form-h2{
  text-align:left;
  font-weight: normal;
  padding: 0px;
  margin: 0px;
  letter-spacing: 1px;
  word-spacing: 4px;
  font-size: 13px;
  width: 20%;
  margin-left: 15%;
}
.form{
  width: 80%;
  margin: 10px;
  margin-top: 0px;
  margin-bottom: 0px;
  background-color: pink;
  padding: 30px;
  display: block;
  float: right;
}
.form-container-title-image{
  text-align: left;
  display: flex;
  width: 100%;
  gap: 12px;
}
.form__project-title{
  text-align: left;
  display: flex;
  flex-direction: column;
  gap: 8px;
  width: 100%;
  margin-bottom: 12px;
  font-weight: bold;
  letter-spacing: 1px;
  font-family: arial;
}
.form__project-image{
  text-align: left;
  display: flex;
  flex-direction: column;
  gap: 8px;
  width: 100%;
  margin-bottom: 12px;
  font-weight: bold;
  letter-spacing: 1px;
  font-family: arial;
}

.form__project-description{
  text-align: left;
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 8px;
  margin-bottom: 12px;
  font-weight: bold;
  letter-spacing: 1px;
  font-family: arial;
}
.button-submit{
  background-color: ivory;
  border: solid 2px ivory;
  padding: 6px 20px;
  letter-spacing: 1px;
  cursor: pointer;
}
.button-submit:hover{
  border: solid 2px black;
}

</style>
