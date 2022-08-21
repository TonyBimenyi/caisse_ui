// eslint-disable-next-line vue/multi-word-component-names
<template>
  <div class="login_container">
    <h1>BIMBO CAISSE APP</h1>
      <div class="form">
        <div class="label">
            <label for="">Username:</label>
        </div>
        <div class="input">
            <input type="text" placeholder="Enter your username...">
        </div>
        <div class="label">
            <label for="">Password:</label>
        </div>
        <div class="input">
            <input type="password" placeholder="Enter your username...">
        </div>
        <div class="rad">
          <div class="radio">
              <input type="radio">Bimbo SuperMarket
          </div>
          <div class="radio">
              <input type="radio">Bimbo Pharma
          </div>
        </div>
        <div class="button">
            <button>Login</button>
        </div>
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style src='../assets/css/login.css' scoped>

</style>