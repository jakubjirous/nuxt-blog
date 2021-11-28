<template>
  <div class="admin-auth-page">
    <div class="auth-container">
      <form>
        <AppControlInput type="email">E-mail Address</AppControlInput>
        <AppControlInput type="password">Password</AppControlInput>
        <AppButton type="submit">{{ appButtonTitle }}</AppButton>
        <AppButton
          type="button"
          btn-style="inverted"
          style="margin-left: 10px"
          @click="onSwitchToLogin">Switch to {{ appButtonInvertedTitle }}
        </AppButton>
      </form>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import AppButton from '~/components/UI/AppButton.vue';
import AppControlInput from '~/components/UI/AppControlInput.vue';

export default Vue.extend({
  name: 'AdminAuthPage',
  components: {
    AppControlInput,
    AppButton
  },
  layout: 'admin',
  data() {
    return {
      isLogin: true
    };
  },
  methods: {
    onSwitchToLogin() {
      this.isLogin = !this.isLogin;
    },
    appButtonTitle() {
      return this.isLogin ? 'Login' : 'Sign Up';
    },
    appButtonInvertedTitle() {
      return this.isLogin ? 'Sign Up' : 'Login';
    }
  }
});
</script>

<style scoped>
.admin-auth-page {
  padding: 20px;
}

.auth-container {
  border: 1px solid #ccc;
  border-radius: 5px;
  box-shadow: 0 2px 2px #ccc;
  width: 300px;
  margin: auto;
  padding: 10px;
  box-sizing: border-box;
}
</style>
