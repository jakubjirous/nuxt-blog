<template>
  <div class="admin-new-post-page">
    <section class="new-post-form">
      <AdminPostForm/>
    </section>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import AdminPostForm from '~/components/Admin/AdminPostForm.vue';

export default Vue.extend({
  name: 'AdminNewPostPage',
  components: {
    AdminPostForm,
  },
  layout: 'admin',
});
</script>

<style scoped>
.admin-new-post-page {
  padding: 30px;
}

.new-post-form {
  width: 90%;
  margin: 20px auto;
}

@media (min-width: 768px) {
  .new-post-form {
    width: 500px;
  }
}
</style>
