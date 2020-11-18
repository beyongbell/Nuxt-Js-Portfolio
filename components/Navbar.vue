<template>
  <div>
    <nav class="navbar" role="navigation" aria-label="main navigation">
      <div class="navbar-brand">
        <nuxt-link to="/" class="navbar-item" href="https://bulma.io">
          <Logo class="logo" />
        </nuxt-link>
      </div>

      <div id="navbarBasicExample" class="navbar-menu">
        <div class="navbar-start">
          <nuxt-link to="/" class="navbar-item"> Home </nuxt-link>

          <nuxt-link to="/blog" class="navbar-item"> Blog </nuxt-link>

          <nuxt-link to="/profile" class="navbar-item"> Profile </nuxt-link>

          <div class="navbar-item has-dropdown is-hoverable">
            <a class="navbar-link"> More </a>

            <div class="navbar-dropdown">
              <nuxt-link to="/about" class="navbar-item"> About </nuxt-link>
              <nuxt-link to="/photos" class="navbar-item"> Jobs </nuxt-link>
            </div>
          </div>
        </div>

        <div class="navbar-end">
          <div class="navbar-item">
            <div class="buttons">
              <nuxt-link to="/login" class="button is-primary">
                <strong>Login</strong>
              </nuxt-link>
            </div>
          </div>
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
.logo {
  width: 32px;
  height: 32px;
}
</style>
