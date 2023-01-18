<script setup>
import AuthPage from "./AuthPage/index.vue";
import ChatsPage from "./ChatsPage/index.vue";
</script>

<template>
  <AuthPage v-if="!user" @onAuth="handleAuth" />
  <ChatsPage v-else v-bind:username="user.username" v-bind:secret="user.secret" />
</template>
<script>
export default {
  data() {
    return {
      user: undefined,
    };
  },
  methods: {
    handleAuth(user) {
      this.user = user;
    },
  },
};
</script>
<style scoped>
/* .logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa); */
</style>
