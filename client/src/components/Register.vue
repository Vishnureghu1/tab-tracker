<template>
  <div>
    <h1>Registeration</h1>

    <input type="email" v-model="email" name="email" placeholder="eamil" />
    <input
      type="password"
      v-model="password"
      name="password"
      placeholder="password"
    />
    <br />
    <button @click="register">Register</button>
  </div>
</template>

<script>
import AuthenticationService from '../services/AuthenticationService'
export default {
  name: 'Register',
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    async register () {
      const response = await AuthenticationService.register({
        email: this.email,
        password: this.password
      })

      console.log('response', response.data)
    }
  }
}
</script>

<style></style>
