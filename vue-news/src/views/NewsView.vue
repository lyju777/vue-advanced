<template>
  <div>
      <div v-for="(user,i) in users" :key="i">{{user}}</div>
  </div>
</template>

<script>
import {fetchNewsList} from '../api/index.js';


export default {

  data(){
    return{
      users: []
    }
  },
  created() {
    console.log("호출 전:",this);
    fetchNewsList()
    .then(response => {
        console.log("호출 후:",this);
      this.users = response.data
    })
    .catch(error => {
      console.log(error);
    })
  }
}
</script>

<style>

</style> 