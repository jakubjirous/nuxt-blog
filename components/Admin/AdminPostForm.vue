<template>
  <form @submit.prevent="onSubmit">
    <AppControlInput v-model="editedPost.author">Author Name</AppControlInput>

    <AppControlInput v-model="editedPost.title">Title</AppControlInput>

    <AppControlInput v-model="editedPost.thumbnailLink">Thumbnail Link</AppControlInput>

    <AppControlInput
      v-model="editedPost.content"
      control-type="textarea">Content
    </AppControlInput>

    <AppButton type="submit">Save</AppButton>

    <AppButton
      type="button"
      style="margin-left: 10px"
      btn-style="cancel"
      @click="onCancel">Cancel
    </AppButton>
  </form>
</template>

<script lang="ts">
import Vue from 'vue';
import AppButton from '~/components/UI/AppButton.vue';
import AppControlInput from '~/components/UI/AppControlInput.vue';

export default Vue.extend({
  name: 'AdminPostForm',
  components: {
    AppControlInput,
    AppButton
  },
  props: {
    post: {
      type: Object,
      required: false,
      default: null,
    }
  },
  data() {
    return {
      editedPost: this.post
        ? { ...this.post }
        : {
          author: '',
          title: '',
          thumbnailLink: '',
          content: '',
        }
    };
  },
  methods: {
    onSubmit() {
      // TODO: save the post
    },
    onCancel() {
      this.$router.push('/admin');
    }
  }
});
</script>

<style scoped>

</style>
