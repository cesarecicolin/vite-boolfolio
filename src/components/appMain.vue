<script>
import axios from 'axios';
export default {
  data(){
    return{
      
      baseUrl:'127.0.0.1:8000',
      projects: []

    }
  },
  created(){
    axios.get('http://127.0.0.1:8000/api/projects')
          .then((resp) => {
            console.log(resp);
            this.projects = resp.data.data

          })
  }
}
</script>

<template>
<div class="container">
    <div class="row row-cols-3">
        <div class="col" v-for="project in projects">
            <div class="card">
            <div class="card-body">
                <h1>{{ project.title }}</h1>
            </div>
        </div>
        </div>
        
    </div>
</div>
</template>

<style lang="scss" scoped>

</style>