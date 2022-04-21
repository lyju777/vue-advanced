<template>
  <div>
    <ul class="news-list">
      <li v-for="(item, i) in this.$store.state.news" :key="i" class="post">
        <!-- 포인트 영역 -->
        <div class="points">
          {{ item.points }}
        </div>
        <!-- 기타 정보 영역 -->
        <div>
          <p class="news-title">
            <a v-bind:href="item.url">
              {{ item.title }}
            </a>
          </p> 
          <small class="link-text">
            {{item.time_ago}} by
            <router-link class="link-text" :to="`/user/${item.user}`">{{
              item.user
            }}</router-link>
          </small>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  created() {
    this.$store.dispatch("FETCH_NEWS");
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
.news-title{
  margin: 0px;
}

.link-text{
  color: #828282;
}
</style>
