<template>
  <div class="posts-page">
    <PostList :posts="loadedPosts"/>
  </div>
</template>

<script lang="ts">
import { Context } from '@nuxt/types';
import Vue from 'vue';
import PostList from '~/components/Posts/PostList.vue';
import { Post } from '~/pages/index.vue';

export default Vue.extend({
  name: 'PostListPage',
  components: {
    PostList
  },
  asyncData(_: Context): Promise<object | void> | object | void {

    const loadedPosts: Post[] = [
      {
        id: '1',
        title: 'Post Title 1',
        previewText: 'Preview Text 1',
        thumbnail: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ3KpGTHO8hqeYRF6iGqQQqgkvh9j6wgN13Hg&usqp=CAU',
        author: 'James',
        updatedDate: new Date(),
        content: 'Content'
      },
      {
        id: '2',
        title: 'Post Title 2',
        previewText: 'Preview Text 2',
        thumbnail: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ3KpGTHO8hqeYRF6iGqQQqgkvh9j6wgN13Hg&usqp=CAU',
        author: 'James',
        updatedDate: new Date(),
        content: 'Content'
      }
    ];

    return {
      loadedPosts
    };
  },
  data() {
    return {
      loadedPosts: []
    };
  }
});
</script>

<style scoped>
.posts-page {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
