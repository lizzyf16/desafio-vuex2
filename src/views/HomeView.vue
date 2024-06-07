<template>
  <div class="home">
  <h1 class="text-center">Tienda 32 Bits</h1>
  <TablaJuegos/>
  </div>
</template>

<script>
import TablaJuegos from '@/components/Tablajuegos.vue'
export default {
  name: 'HomeView',
  components: {
    TablaJuegos
  }
}
</script>
