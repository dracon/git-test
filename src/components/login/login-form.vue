<template>
  <form class="form">
    <div class="form-title">Login</div>
    <div class="form-group">
      <label class="form-label" for="email">Email</label>
      <input class="form-input" type="email" id="email" v-model="email">
    </div>
    <div class="form-group">
      <label class="form-label" for="password">Password</label>
      <input v-if="!showPw" class="form-input" type="password" id="password" v-model="password">
      <input v-if="showPw" class="form-input" type="text" v-model="password">
      <password-show></password-show>
    </div>
    <div class="form-group">
      <div class="button-group">
        <button class="btn btn-send" @click="sendLogin(email, password, $event)">Login</button>
        <button v-if="showMe">TEST</button>
      </div>
    </div>
  </form>
</template>
<script>
  import PasswordShow from './password-show.vue'

  export default {
    name: 'LoginForm',
    components: {
      PasswordShow
    },
    data: function () {
      return {
        email: '',
        password: '',
        showPw: false,
        showMe: null,
        type: 'password'
      }
    },
    methods: {
      sendLogin: (em, pw, event) => {
//        let vm = this
        console.log(pw)
        setTimeout(function () {
          console.log(em)
        }, 100)
      }
    },
    mounted () {
      let vm = this
      vm.$on('showpass', function (val) {
        vm.showPw = val
      })
    }
  }
</script>
<style lang="scss">
  .form {
    background: rgba(90, 20, 120, 0.11);
    padding: 10px 20px;
    width: 300px;
    margin: auto;
    color: #666;
    box-shadow: 3px 3px 5px rgba(0, 0, 0, 0.2);
    .form-title {
      font-size: 1.6em;
      padding: 5px 0;
      text-align: left;
    }
    .form-group {
      display: flex;
      align-items: center;
      justify-content: flex-end;
      text-align: right;
      margin-bottom: 5px;
      &:last-child {
        margin-bottom: 0;
      }
      .form-label {
        margin-right: 1em;
      }
      .form-input {
        padding: 5px;
        border: none;
        background-color: white;
        &:focus {
          box-shadow: 0 0 3px red;
        }
      }
      .button-group {
        padding: 10px 0;
      }
      .btn {
        border: none;
        padding: 5px 10px;
        background: white;
        box-shadow: 0 0 3px rgba(0, 0, 0, 0.2);
        transition: all 0.5s;
        cursor: pointer;
        &:hover {
          background: rgba(0, 0, 0, 0.1);
        }
        &.btn-show-pw {
          position: absolute;
        }
      }
    }
  }
</style>
