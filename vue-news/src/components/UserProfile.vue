<template>
  <div class="user-container">
    user <br />
    <div>
      <slot name="username">
        <!-- 상위 컴포넌트에서 정의할 영역 -->
      </slot>
    </div>
    <div>
      <slot name="time">
        <!-- 상위 컴포넌트에서 정의할 영역 -->
      </slot>
    </div>
    <div>
      <slot name="karma"></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    info: Object,
  },
};
</script>

<style scoped>
.user-container {
  display: flex;
}
</style>