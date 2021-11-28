<template>
  <div class="admin-page">
    <section class="new-post">
      <AppButton @click="newPostLink">Create Post</AppButton>
      <AppButton
        style="margin-left: 10px"
        btn-style="cancel"
        @click="rootLink"
      >
        Back to Blog
      </AppButton>
    </section>
    <section class="existing-posts">
      <h1>Existing Posts</h1>
      <PostList :posts="loadedPosts" is-admin/>
    </section>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import PostList from '~/components/Posts/PostList.vue';
import AppButton from '~/components/UI/AppButton.vue';

export default Vue.extend({
  name: 'AdminPage',
  components: {
    AppButton,
    PostList
  },
  layout: 'admin',
  methods: {
    newPostLink() {
      return this.$router.push('/admin/new-post');
    },
    rootLink() {
      return this.$router.push('/');
    }
  }
});
</script>

<style scoped>
.admin-page {
  padding: 30px;
}

.new-post {
  text-align: center;
  border-bottom: 2px solid #ccc;
  padding-bottom: 10px;
}

.existing-posts h1 {
  text-align: center;
}
</style>
