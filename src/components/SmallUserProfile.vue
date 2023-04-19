<template>
  <div>
    <h3>{{ user[`name`] }}</h3>
    <p>{{ user[`age`] }}</p>
    <h5 v-if="user[`is_premium`] === true">PREMIUM</h5>
    <p v-else>Basic</p>
    <button @click="user_clicked">CLICK ME</button>
  </div>
</template>

<script>
export default {
  methods: {
    user_clicked() {
      this.$emit(`user_clicked`, this.user[`name`]);
    },
  },
  props: {
    user: Object,
  },
};
</script>

<style scoped>
</style>