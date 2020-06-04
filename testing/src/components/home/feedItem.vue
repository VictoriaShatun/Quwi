<template>
  <div class="feed-item">
  </div>
</template>

<style scoped>
.feed-item {
  padding: 1em;
  width: 350px;
}
</style>
<script>
export default {
  name: "feedItem",
  props: { feed: Object }
};
</script>
