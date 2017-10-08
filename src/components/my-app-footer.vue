<template>
  <div class="footer">
    <div class="footer-item col-4">BOX 1</div>
    <div class="footer-item col-4">BOX 2</div>
    <div class="footer-item col-4">BOX 3</div>
    <div class="footer-item col-4">BOX 4</div>


  </div>
</template>
<script>
  export default {
    name: 'MyAppFooter'
  }
</script>
<style lang="scss">
  .footer {
    display: flex;
    align-items: stretch;
    justify-content: space-around;
    box-sizing: border-box;
    position: fixed;
    flex-wrap: wrap;
    bottom: 0;
    left: 0;
    width: 100%;
    min-height: 60px;
    padding: 10px;
    background: #35495e;
    color: aliceblue;
    .footer-item {
      box-sizing: border-box;
      background: red;
      display: flex;
      align-items: flex-start;
      min-height: 60px;
    }
  }

  .col-4 {
    width: 24%;
    padding: 5px;
    min-width: 150px;
    margin-bottom: 10px;
  }

  @media screen and (max-width: 600px) {
    .footer {
      position: relative;
      flex-direction: column;
      justify-content: center;
      margin-top: 2em;
      width: 100%;
      .footer-item {
      }
    }
    .col-4 {
      width: 100%;
    }
  }

  @media screen and (min-width: 600px) and (max-width: 1000px) {
    .footer {
      position: relative;
      bottom: 0;
      flex-direction: row;
      margin-top: 2em;
      .footer-item {
      }
    }
    .col-4 {
      width: 48%;
    }
  }
</style>
