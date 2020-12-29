<template>
  <div>
    <nav class="navbar flex-sm-column navbar-expand-lg navbar-light bg-light">
      <div class="container-fluid">
        <div class="collapse navbar-collapse">
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <nuxt-link no-prefetch exact class="nav-item" active-class="active" to="/params">
              Параметры
            </nuxt-link>
            <nuxt-link no-prefetch exact class="nav-item" active-class="active" to="/questions">
              Вопросы
            </nuxt-link>
            <nuxt-link no-prefetch exact class="nav-item" active-class="active" to="/logic">
              Логика
            </nuxt-link>
            <nuxt-link no-prefetch exact class="nav-item" active-class="active" to="/conditions">
              Условия
            </nuxt-link>
            <nuxt-link no-prefetch exact class="nav-item" active-class="active" to="/respondents/NewForm">
              Респонденты
            </nuxt-link>
          </ul>
        </div>
      </div>
    </nav>
    <div>

    </div>
  </div>
</template>
<script>

export default {
  components: {
  }
}

</script>
