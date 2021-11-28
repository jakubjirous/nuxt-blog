<template>
  <section class="posts-list">
    <PostPreview
      v-for="post in posts"
      :id="post.id"
      :key="post.id"
      :title="post.title"
      :preview-text="post.previewText"
      :thumbnail="post.thumbnail"
      :is-admin="isAdmin"
    />
  </section>
</template>

<script lang="ts">
import Vue from 'vue';
import PostPreview from '~/components/Posts/PostPreview.vue';

export default Vue.extend({
  name: 'PostList',
  components: {
    PostPreview
  },
  props: {
    isAdmin: {
      type: Boolean,
      default: false
    },
    posts: {
      type: Array,
      required: true,
    }
  }
});
</script>

<style scoped>
.posts-list {
  display: flex;
  padding: 20px;
  box-sizing: border-box;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
}
</style>
