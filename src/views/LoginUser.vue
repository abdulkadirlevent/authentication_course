<template>
  <div>
    <AuthForm @submitForm="login" />
  </div>
</template>

<script>
import AuthForm from '@/components/AuthForm.vue';
export default {
  components: {
    AuthForm
  },
  methods: {
    login ({email, password}) {
      this.$store
        .dispatch('login', {
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
