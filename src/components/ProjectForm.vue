<template>
  <div class="formBody">
    <h3>Project Title</h3>
    <textarea></textarea>
    <h3>Project Description</h3>
    <textarea></textarea>
    <h3>Setup Instructions:</h3>
    <div>
      <input type="checkbox" name="useVue" />
      <label for="useVue"> Vue</label>
    </div>
    <button class="generateBtn">Generate</button>
  </div>
</template>

<script>
export default {
  name: "ProjectForm",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.formBody {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  background-color: rgb(80,80,90);
  padding: 0.6em;
  border-radius: 2%;
  color: #e7e7e7;
  > textarea {
    min-width: min(80vw, 50em);
    min-height: min(20vh, 20em);
  }
  .generateBtn {
    margin-left: auto;
    margin-right: auto;
    font-size: 1.3em;
    padding: 0.4em;
    background-color: rgb(70,70,90);
    color: white;
    border-radius: 5%;
    &:hover {
      background-color: rgb(80,80,100);
    }
    &:active {
      background-color: rgb(60,60,80);
    }
  }
}
</style>
