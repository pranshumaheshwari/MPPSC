<template>
  <div id="wrapper">
    <h1>MPPSC Ranklist Software</h1>
    <div class="Login row">
      <div class="col-sm-3"></div>
      <div class="col-sm-6">
        <LoginForm />
      </div>
      <div class="col-sm-3"></div>
    </div>
  </div>
</template>

<script>
  import LoginForm from './LandingPage/LoginForm'

  export default {
    name: 'landing-page',
    components: { LoginForm }
  }
</script>

<style lang="scss">
  #wrapper {
    height: 100vh;
    padding: 60px 80px;
    width: 100vw;
    h1 {
      margin-left: 14vw;
      margin-top: 5vh;
    }
  }
  
  .Login {
    margin-top: 15%;
  }
</style>
