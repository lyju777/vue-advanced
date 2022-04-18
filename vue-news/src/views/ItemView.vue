<template>
  <div>
    <section>
      <!-- 질문 상세 정보 -->
      <div class="user-container">
        user <br />
        <div>
          <router-link :to="`/user/${fetchedItem.user}`">
            {{ fetchedItem.user }}
          </router-link>
        </div>
        <div>
          <router-link>
            {{ fetchedItem.time.ago }}
          </router-link>
        </div>
        <h2>{{ fetchedItem.title }}</h2>
      </div>
    </section>
    <section>
      <!-- 질문 댓글, -->
      <div v-html="fetchedItem.content"></div>
    </section>
    <!-- {{ this.$store.state.item}} -->
    <!-- <p>  {{ fetchedItem.title}} </p>
      <div> {{ fetchedItem.content}}</div> -->
  </div>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  computed: {
    ...mapGetters(["fetchedItem"]),
  },

  created() {
    const itemId = this.$route.params.id;
    this.$store.dispatch("FETCH_ITEM", itemId);
  },
};
</script>

<style scoped>
.user-container {
  display: flex;
}
</style>