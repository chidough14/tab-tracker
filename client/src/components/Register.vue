<template>
    <div>
        <h1>Register</h1>
        <input
        type="email"
        name="email"
        v-model="email"
        placeholder="Email"/>
         <br>
        <input
        type="password"
        name="password"
        v-model="password"
        placeholder="Password"/>
        <br>
        <button @click="register">Register</button>
    </div>


</template>

<script>
    import AuthenticationService from '@/services/AuthenticationService'
    export default {
      data () {
        return {
          email: '',
          password: ''
        }
      },
      methods: {
        async register () {
          await AuthenticationService.register({
            email: this.email,
            password: this.password
          })
        }
      }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
