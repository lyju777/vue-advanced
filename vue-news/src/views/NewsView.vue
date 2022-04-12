<template>
  <div>
      <p v-for="(item,i) in this.$store.state.news" :key="i">
        <a v-bind:href="item.url">
          {{item.title}}
          </a>
          <small>{{item.time_ago}} by {{item.user}}</small>
        </p>
  </div>
</template>

<script>

export default {

  created() {

    this.$store.dispatch('FETCH_NEWS');
  },
}
</script>

<style>

</style> 