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
        <input type="text" placeholder="Username" class="form-control" id="username" name="username">
      </div>
      <div class="form-group">
        <input type="password" placeholder="Password" class="form-control" id="password" name="password">
      </div>
      <input type="submit" class="btn btn-dark"> 
    </form>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        error: ''
      }
    },
    methods: {
      formSubmit: function (e) {
        // Check For User In DB
        // If user with username exists and password is correct then login else error
        let _this = this
        this.$db.find({'user.username': e.target.querySelector('#username'), 'user.password': e.target.querySelector('#password').value}, function (err, user) {
          if (err) {
            _this.error = err
            return
          }
          if (!user.length) {
            _this.error = `The username or password you entered is incorrect.`
            return
          }
          _this.$router.push({path: '/home'})
        })
      }
    }
  }
</script>

<style scoped>

</style>
