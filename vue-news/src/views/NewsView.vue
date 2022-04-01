<template>
  <div>
      <div v-for="(user,i) in users" :key="i">{{user}}</div>
  </div>
</template>

<script>
import axios from 'axios';

export default {

  data(){
    return{
      users: []
    }
  },
  created() {
    var vm = this;
    axios.get('https://api.hnpwa.com/v0/news/1.json')
    .then(function(response){
        console.log(response);
        vm.users = response.data;
    })
    .catch( )
  }
}
</script>

<style>

</style> 