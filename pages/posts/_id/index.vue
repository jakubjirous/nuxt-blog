<template>
  <div class="single-post-page">
    <section class="post">
      <h1 class="post-title">{{ loadedPost.title }}</h1>
      <div class="post-details">
        <div class="post-detail">Last updated on {{ loadedPost.updatedDate.toLocaleDateString() }}</div>
        <div class="post-detail">Written by {{ loadedPost.author }}</div>
      </div>
      <p class="post-content">
        {{ loadedPost.content }}
      </p>
    </section>
    <section class="post-feedback">
      <p>
        Let me know what you think about the post, send a email to <a href="mailto:feedback@my-awesome-domain.com">feedback@my-awesome-domain.com</a>
      </p>
    </section>
  </div>
</template>

<script lang="ts">
import { Context } from '@nuxt/types';
import Vue from 'vue';
import { Post } from '~/pages/index.vue';

export default Vue.extend({
  name: 'PostDetailPage',
  asyncData(ctx: Context): Promise<object | void> | object | void {

    const loadedPost: Post = {
      id: '1',
      title: `Post Title 1 (ID: ${ctx.route.params.id})`,
      previewText: 'Preview Text 1',
      thumbnail: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ3KpGTHO8hqeYRF6iGqQQqgkvh9j6wgN13Hg&usqp=CAU',
      author: 'James',
      updatedDate: new Date(),
      content: 'Content'
    };

    return {
      loadedPost
    };
  },
  data() {
    return {
      loadedPost: null
    };
  }
});
</script>

<style scoped>
.single-post-page {
  padding: 30px;
  text-align: center;
  box-sizing: border-box;
}

.post {
  width: 100%;
}

@media (min-width: 768px) {
  .post {
    width: 600px;
    margin: auto;
  }
}

.post-title {
  margin: 0;
}

.post-details {
  padding: 10px;
  box-sizing: border-box;
  border-bottom: 3px solid #ccc;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

@media (min-width: 768px) {
  .post-details {
    flex-direction: row;
  }
}

.post-detail {
  color: rgb(88, 88, 88);
  margin: 0 10px;
}

.post-feedback a {
  color: red;
  text-decoration: none;
}

.post-feedback a:hover,
.post-feedback a:active {
  color: salmon;
}
</style>
