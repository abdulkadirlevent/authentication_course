<template>
  <div>
    <AuthForm @submitForm="register" :askName="true" />
  </div>
</template>

<script>
import AuthForm from '@/components/AuthForm.vue';
export default {
  components: {
    AuthForm
  },
  methods: {
    register ({name, email, password}) {
      this.$store
        .dispatch('register', {
          name,
          email,
          password
        })
        .then(() => {
          this.$router.push({ name: 'dashboard' })
        })
    }
  }
}
</script>

<style scoped>
</style>
