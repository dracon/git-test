<template>
  <button
    class="btn btn-show-pw"
    @mousedown.stop.prevent="showPassWord(true)"
    @mouseup.stop.prevent="showPassWord(false)"
    @mouseleave.stop.prevent="showPassWord(false)"
    @click.stop.prevent="showPassWord(false)"
  >
    Ø
  </button>
</template>
<script>
  export default {
    name: 'PasswordShow',
    data () {
      return {
      }
    },
    methods: {
      showPassWord: function (val) {
        this.$parent.$emit('showpass', val)
      }
    }
  }
</script>
<style>
</style>
