<template>
  <my-comment v-for="comment in comments">qwe</my-comment>
</template>

<script>
import MyComment from "./MyComment.vue";
export default {
  components: {
    MyComment,
  },
  props: {
    comments: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped></style>
