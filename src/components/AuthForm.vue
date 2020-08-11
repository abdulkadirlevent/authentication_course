<template>
  <form @submit.prevent="$emit('submitForm', {email, password, name})">
    <template v-if="askName">
      <label for="name">
        Name:
      </label>
      <input v-model="name" type="text" name="name" value>
    </template>

    <label for="email">
      Email:
    </label>
    <input v-model="email" type="email" name="email" value>

    <label for="password">
      Password:
    </label>
    <input v-model="password" type="password" name="password" value>

    <button type="submit" name="button">
      Login
    </button>
    <router-link to="/register">
      Don't have an account? Register.
    </router-link>
  </form>
</template>

<script>
  export default {
    data () {
      return {
        email: '',
        password: '',
        name: ''
      }
    },
    props: {
      askName: {
        type: Boolean,
        default: false
      }
    }
  }
</script>

<style lang="scss" scoped>

</style>