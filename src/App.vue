<template>
  <div id="app">
    <h1>Readme Generator</h1>
    <ProjectForm />
  </div>
</template>

<script>
import ProjectForm from "./components/ProjectForm.vue";

export default {
  name: "App",
  components: {
    ProjectForm
  }
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #e7e7e7;
  display: flex;
  flex-direction: column;
  align-items: center;
}
body{
  background-color: rgb(30,30,35);
}
</style>
