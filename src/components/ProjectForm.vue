<template>
  <div class="formBody">
    <h3>Project Title</h3>
    <input type="text" v-model="title"/>
    <h3>Project Description</h3>
    <textarea v-model="desc"></textarea>
    <h3>Demo Link</h3>
    <input type="text" v-model="demoUrl"/>
    <h3>Setup Instructions:</h3>
    <div>
      <input type="checkbox" name="useVue" v-model="useVue" />
      <label for="useVue"> Vue</label>
    </div>
    <button class="generateBtn" @click="downloadFile">Generate</button>
  </div>
</template>

<script>
export default {
  name: "ProjectForm",
  data: function(){
    return{
      title: "",
      desc: "",
      demoUrl: "",
      useVue: false
    }
  },
  methods: {
    generateFileText(){
      let result = ""
      if(this.title.trim() != ""){
        result += "# "+this.title+"\n";
      }
      if(this.demoUrl.trim() != ""){
        result += "**[Live Demo]("+this.demoUrl+")**\n"
      }
      if(this.desc.trim() != ""){
        result += "\n"+this.desc+"\n\n";
      }
      if(this.useVue){
        result +="## Project Setup\n```\nnpm install\n```\n\n### Compiles and hot-reloads for development\n```\nnpm run serve\n```\n\n### Compiles and minifies for production\n```\nnpm run build\n``` "
      }

      return result
    },
    downloadFile(){
      let data = this.generateFileText();
      let filename = "README.md"

      //adapted from https://stackoverflow.com/questions/9208657/how-to-create-downloadable-link-to-text-file
      let file = new Blob([data], {type: "text/plain"});
      if (window.navigator.msSaveOrOpenBlob) // IE10+
          window.navigator.msSaveOrOpenBlob(file, filename);
      else { // Others
          let a = document.createElement("a"),
          url = URL.createObjectURL(file);
          a.href = url;
          a.download = filename;
          document.body.appendChild(a);
          a.click();
          setTimeout(function() {
              document.body.removeChild(a);
              window.URL.revokeObjectURL(url);
          }, 0);
      }

    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.formBody {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  background-color: rgb(80,80,90);
  padding: 1em;
  border-radius: 2%;
  color: #e7e7e7;
  > input, > textarea {
    width: 100%;
    font-size: 1em;
    font-weight: bold;
  }
  > textarea {
    min-width: min(80vw, 45em);
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
