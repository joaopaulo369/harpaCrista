<script setup>
import CardHinoVue from '@/components/CardHino.vue';
import { reactive, ref, computed, watch } from 'vue';
import harpaJson from '../assets/harpa_crista.json';

const harpa = reactive(Object.entries(harpaJson).map(([key, value]) => ({ id: key, ...value })));

// iniciando pesquisar
let pesquisarHino = ref('');
const scrollArea = ref(null);

const HinosFiltrados = computed(() => {
  if (harpa && pesquisarHino.value) {
    return harpa.filter(hino => hino.hino && hino.hino.toLowerCase().includes(pesquisarHino.value.toLowerCase()));
  }
  return harpa;
});

watch(pesquisarHino, () => {
  scrollArea.value.scrollTo({ top: 0, behavior: 'smooth' }); // 'smooth' adiciona a animação de rolagem
});

// console.log(harpa)
// console.log(HinosFiltrados.value)

</script>

<template>
  <main>
    <div class="container">
      <div class="my-3">
        <label hidden for="pesquisa" class="form-label">Pesquisar por hino:</label>
        <input v-model="pesquisarHino" type="text" class="form-control" id="pesquisa" placeholder="Pesquisar...">
      </div>
      <hr>
      <div ref="scrollArea" class="lista-hinos overflow-x-auto">
        <CardHinoVue v-for="hino in HinosFiltrados" :key="hino.id" :hino="hino" />
      </div>

    </div>
  </main>
</template>

<style scoped>
.lista-hinos {
  height: 100vh;
}
</style>
