<template>
  <div>
    <list-item></list-item>
  </div>
</template>

<script>
import ListItem from '@/components/ListItem.vue';
export default {
  components: { ListItem },
  created() {
    this.$store.dispatch("FETCH_JOBS");
  },
};
</script>

<style scoped>
.news-list {
  margin: 0px;
  padding: 0px;
}
.post {
  list-style: none;
  display: flex;
  align-items: center;
  border-bottom: 1px solid #eee;
}

.points {
  width: 80px;
  height: 60px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #42b833;
}
.news-title {
  margin: 0px;
}

.link-text {
  color: #828282;
}
</style>