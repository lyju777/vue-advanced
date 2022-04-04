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
    var vm = this;
    fetchNewsList()
    .then(function(response){
        console.log(response);
        vm.users = response.data;
    })
    .catch()
  }
}
</script>

<style>

</style> 