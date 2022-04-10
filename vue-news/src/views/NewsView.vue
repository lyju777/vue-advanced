<template>
  <div>
      <div v-for="(user,i) in this.$store.state.news" :key="i">{{user}}</div>
  </div>
</template>

<script>

export default {

  created() {

    this.$store.dispatch('FETCH_NEWS');

    // // 1
    // fetchNewsList()
    // .then(response => {
    //     console.log("호출 후:",this);

    //   //2
    //   this.users = response.data
    // })
    // .catch(error => {
    //   console.log(error);
    // })
  }
}
</script>

<style>

</style> 