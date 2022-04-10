<template>
  <div>
      <div v-for="(item,i) in fetchedAsk" :key="i">{{item.title}}</div>
  </div>
</template>

<script>
import { mapGetters } from 'vuex';

export default {

  computed: {
    ...mapGetters([
      'fetchedAsk'
    ]),
    // 2#
    // ...mapState({
    //   ask: state => state.ask
    // })

    // 1#
    // // ask() {
    // //   return this.$store.state.ask
    // // }
  },

  created() {
    this.$store.dispatch('FETCH_ASK');
},
}
</script>

<style>

</style>