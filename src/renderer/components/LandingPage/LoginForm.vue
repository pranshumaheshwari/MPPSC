<template>
  <div>
    <form @submit.prevent="formSubmit" class="form-horizontal">
      <legend>
        Login
      </legend>
      <div v-if="error" class="alert alert-danger">
        {{ error }}
      </div>
      <div class="form-group">
        <input type="text" placeholder="Username" class="form-control" id="username" name="username" v-model="username">
      </div>
      <div class="form-group">
        <input type="password" placeholder="Password" class="form-control" id="password" name="password" v-model="password">
      </div>
      <input type="submit" class="btn btn-dark"> 
    </form>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        error: '',
        username: '',
        password: ''
      }
    },
    methods: {
      formSubmit: function () {
        // Check For User In DB
        // If user user exists and password is correct
        // this.$route.push(path to next route)
        // else this.error = error
      }
    }
  }
</script>

<style scoped>

</style>
