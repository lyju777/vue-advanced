<template>
  <div>
      <div v-for="(item,i) in ask" :key="i">{{item.title}}</div>
  </div>
</template>

<script>
import {fetchAskList} from '../api/index.js';

export default {

  data(){
    return {
      ask: []
    }
  },

  created() {
    var vm = this;
    fetchAskList()
    .then((response)=> {
      vm.ask = response.data;
    })
    .catch((error)=> {
      console.log(error);
    });
  },

}
</script>

<style>

</style>