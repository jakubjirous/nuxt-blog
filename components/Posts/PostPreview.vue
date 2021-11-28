<template>
  <nuxt-link :to="postDetailUrl" class="post-preview">
    <article>
      <div class="post-thumbnail"
           :style="{ backgroundImage: `url(${ thumbnail })` }">
      </div>
      <div class="post-content">
        <h1>{{ title }}</h1>
        <p>{{ previewText }}</p>
      </div>
    </article>
  </nuxt-link>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'PostPreview',
  props: {
    id: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    previewText: {
      type: String,
      required: true,
    },
    thumbnail: {
      type: String,
      required: true,
    },
    isAdmin: {
      type: Boolean,
      default: true
    }
  },
  computed: {
    postDetailUrl() {
      return this.isAdmin
        ? `/admin/${this.id}`
        : `/posts/${this.id}`;
    },
  }
});
</script>

<style scoped>
a {
  text-decoration: none;
  color: black;
}

.post-preview {
  border: 1px solid #ccc;
  box-shadow: 0 2px 2px #ccc;
  background-color: white;
  width: 90%;
}

@media (min-width: 850px) {
  .post-preview {
    width: 400px;
    margin: 10px;
  }
}

.post-thumbnail {
  width: 100%;
  height: 200px;
  background-position: center;
  background-size: cover;
}

.post-content {
  padding: 10px;
  text-align: center;
}

a:hover .post-content,
a:active .post-content {
  background-color: #ccc;
}
</style>
