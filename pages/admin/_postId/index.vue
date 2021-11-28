<template>
  <div class="admin-post-page">
    <section class="update-form">
      <AdminPostForm :post="loadedPost"/>
    </section>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import AdminPostForm from '~/components/Admin/AdminPostForm.vue';

export default Vue.extend({
  name: 'AdminPostDetailPage',
  components: {
    AdminPostForm
  },
  layout: 'admin',
  data() {
    return {
      loadedPost: {
        author: 'James',
        title: 'Test',
        thumbnailLink: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ3KpGTHO8hqeYRF6iGqQQqgkvh9j6wgN13Hg&usqp=CAU',
        content: 'Testing Post',
      }
    };
  }
});
</script>

<style scoped>
.admin-post-page {
  padding: 30px;
}

.update-form {
  width: 90%;
  margin: 20px auto;
}

@media (min-width: 768px) {
  .update-form {
    width: 500px;
  }
}
</style>
