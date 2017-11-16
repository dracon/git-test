<template>
  <div id="app">
    <header>
      <span>{{ msg }}</span>

      <div class="nav-wrapper">
        <ul class="nav-list">
          <li>
            <router-link to="/">Home</router-link>
          </li>
          <li>
            <router-link to="/login">Login</router-link>
          </li>
        </ul>
      </div>


    </header>
    <main>
      <img src="./assets/logo.png" alt="Vue.js PWA">
      <router-view></router-view>
    </main>
    <footer>
      <my-app-footer></my-app-footer>
    </footer>
  </div>
</template>

<script>
  import myConst from './index'
  import myAppFooter from './components/my-app-footer'

  export default {
    name: 'app',
    components: {
      myAppFooter
    },
    data () {
      return {
        talk: myConst.myConst,
        msg: ''
      }
    },
    mounted: function () {
      let vm = this
      vm.msg = vm.talk.sayHello('My lovely App')
    }
  }
</script>

<style lang="scss">
  body {
    margin: 0;
  }

  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
  }

  main {
    text-align: center;
    margin-top: 40px;
    margin-bottom: 120px;
  }

  header {
    margin: 0;
    height: 56px;
    padding: 0 16px 0 24px;
    background-color: #35495E;
    color: #ffffff;
    display: flex;
    align-items: center;
    justify-content: space-between;
    span {
      display: block;
      position: relative;
      font-size: 20px;
      line-height: 1;
      letter-spacing: .02em;
      font-weight: 400;
      box-sizing: border-box;
      padding-top: 16px;
    }
    .nav-wrapper {
      display: flex;
      align-items: center;
      justify-content: flex-end;
      height: 100%;
      .nav-list {
        display: flex;
        justify-content: flex-start;
        align-items: stretch;
        height: 2em;
        line-height: 2em;
        li {
          display: block;
          background: white;
          margin-right: 2px;
          a {
            padding: 5px 10px;
          }
        }
      }
    }
  }
</style>
