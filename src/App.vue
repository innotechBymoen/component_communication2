<template>
  <div id="app">
    <h1>{{ username }}</h1>
    <small-user-profile
      v-for="(user, i) in users"
      :key="i"
      :user="users[i]"
      @user_clicked="handle_user_clicked"
    >
    </small-user-profile>
  </div>
</template>

<script>
import SmallUserProfile from "@/components/SmallUserProfile.vue";

export default {
  methods: {
    handle_user_clicked: function (name) {
      this.username = name;
    },
  },
  data() {
    return {
      username: undefined,
      users: [
        {
          name: `Bob User`,
          age: 27,
          is_premium: true,
          id: 16678,
        },
        {
          name: `Alice Admin`,
          age: 34,
          is_premium: false,
          id: 42,
        },
      ],
    };
  },
  name: "App",
  components: {
    SmallUserProfile,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
