<template>
  <div>
        <div v-for="(job,i) in this.$store.state.jobs" :key="i">{{job.title}}</div>
  </div>
</template>

<script>

export default {


created() {
  this.$store.dispatch('FETCH_JOBS')
}

}
</script>

<style>

</style>