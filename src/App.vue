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
  color: #2c3e50;
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
