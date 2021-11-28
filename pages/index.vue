<template>
  <div class="home-page">
    <section class="intro">
      <h1>Get the latest tech news!</h1>
    </section>
    <PostList :posts="loadedPosts"/>
  </div>
</template>

<script lang="ts">
import { Context } from '@nuxt/types';
import Vue from 'vue';
import PostList from '~/components/Posts/PostList.vue';

export interface Post {
  id: string,
  title: string,
  previewText: string,
  thumbnail: string,
  author: string,
  updatedDate: Date,
  content: string,
}

export default Vue.extend({
  name: 'IndexPage',
  components: {
    PostList
  },
  asyncData(ctx: Context): Promise<object | void> | object | void {
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

    return new Promise((resolve, reject) => {
      resolve({
        loadedPosts
      });
      reject(new Error('Error'));
    }).then(data => {
      return data;
    }).catch((error) => {
      ctx.error(error);
    });
  },
  data() {
    return {
      loadedPosts: []
    };
  },
});
</script>

<style>
.intro {
  height: 250px;
  position: relative;
  box-sizing: border-box;
  background-position: center;
  background-size: cover;
  background-image: url("assets/images/bg-image.jpg");
  display: flex;
  justify-content: center;
  align-items: center;
}

.intro h1 {
  width: 90%;
  font-size: 1.5rem;
  color: black;
  background-color: rgb(211, 211, 211);
  padding: 1rem 2rem;
  margin-top: 1rem;
  border-radius: 10px;
  box-shadow: 3px 3px 3px black;
  box-sizing: border-box;
  border: 1px solid black;
}

@media (min-width: 768px) {
  .intro h1 {
    font-size: 2rem;
  }
}
</style>
