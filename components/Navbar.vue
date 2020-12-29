<template>
  <nav class="navbar flex-sm-column navbar-expand-lg navbar-light bg-light">
    <div class="container-fluid">
      <div class="collapse navbar-collapse">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <nuxt-link no-prefetch exact class="nav-item" active-class="active" to="/poll">
            Опросы
          </nuxt-link>
          <nuxt-link no-prefetch exact class="nav-item" active-class="active" to="/users">
            Пользователи
          </nuxt-link>
          <nuxt-link no-prefetch exact class="nav-item" active-class="active" to="/blacklist">
            Черный список
          </nuxt-link>
          <nuxt-link no-prefetch exact class="nav-item" active-class="active" to="/call-center">
            Колл-цетр
          </nuxt-link>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
name: "Navbar"
}
</script>

<style scoped>

</style>
