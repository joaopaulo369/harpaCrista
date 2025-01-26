<script setup>
import { RouterLink, RouterView } from 'vue-router'
import navbar from './components/navbar.vue'
import rodapeVue from './components/rodape.vue'
</script>

<template>
  <div class="tamanho d-flex flex-column ">


    <nav class="navbar bg-success">
      <div class="container">
        <button class="btn" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasScrolling"
          aria-controls="offcanvasScrolling">
          <a class="navbar-brand" href="#">
            <i class="bi bi-list"></i>
            Harpa Cristã
          </a>
        </button>

      </div>
    </nav>
    <header><!-- menu ofcavas -->
      <div class="offcanvas offcanvas-start bg-canvas" data-bs-scroll="true" data-bs-backdrop="false" tabindex="-1"
        id="offcanvasScrolling" aria-labelledby="offcanvasScrollingLabel">

        <div class="offcanvas-header bg-success">
          <h5 class="offcanvas-title" id="offcanvasScrollingLabel">
            <span class="titulo-da-harpa">Harpa Cristã </span>
          </h5>
          <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close"></button>
        </div>

        <div class="offcanvas-body">
          <navbar />
        </div>
      </div>
    </header><!-- fim do menu ofcavas -->
    <div class="flex-fill">
      <RouterView />
    </div>
    <rodapeVue />
  </div>
</template>

<style scoped>
.tamanho {
  height: 100vh;
}

.titulo-da-harpa {
  font-weight:600;
  font-size: 1.5rem;
}

.bg-canvas {
  background-color: #D3E4CD;
}
</style>
