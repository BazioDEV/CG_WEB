<template>
  <div id="wrapper">
    <nav class="navbar is-dark">
      <div class="navbar-brand">
        <router-link to="/" class="navbar-item"><strong>Clover Glove</strong></router-link>
        <a class="navbar-burger" aria-label="menu" aria-expanded='false' data-target="navbar-menu">
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
        </a>
      </div>

      <div class="navbar-menu" id="navbar-menu">
        <div class="navbar-end">
          <router-link to="/home" class="navbar-item">Home</router-link>
          <router-link to="/about" class="navbar-item">About</router-link>

          <div class="navbar-item">
            <div class="buttons">
              <router-link to="/log-in" class="button is-light">Login</router-link>

              <router-link to='/cart' class="button is-success">
              <span class="icon"><i class="fa fas-shopping-cart"></i></span>
              <span>Cart</span>
              </router-link>
            </div>
          </div>
        </div>
      </div>
    </nav>
  </div>
  <router-view/>
</template>

<style lang="scss">
@import '../node_modules/bulma';
</style>
