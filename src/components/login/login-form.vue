<template>
  <form class="form">
    <div class="form-group">
      <label class="form-label" for="email">Email</label>
      <input class="form-input" type="email" id="email">
    </div>
    <div class="form-group">
      <label class="form-label" for="password">Password</label>
      <input class="form-input" type="password" id="password">
    </div>
  </form>
</template>
<script>
  export default {
    name: 'LoginForm',
    data () {
      return {
        email: '',
        password: ''
      }
    }
  }
</script>
<style lang="scss">
  .form {
    background: silver;
    padding: 20px;
    width: 300px;
    margin: auto;
    .form-group {
      display: flex;
      align-items: center;
      justify-content: flex-end;
      text-align: right;
      .form-label {

      }
      .form-input {

      }
    }
  }
</style>
