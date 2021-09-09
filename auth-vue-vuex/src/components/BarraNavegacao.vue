<template>
    <nav class="navbar navbar-expand-lg navbar-bytebank">
      <a class="navbar-brand" href="#">ByteBank</a>
      <button class="navbar-toggler" type="button">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <BarraNavegacaoLogado v-if="usuarioLogado" />
        <BarraNavegacaoDeslogado v-else />
      </div>
    </nav>
</template>

<script>
import BarraNavegacaoLogado from './BarraNavegacaoLogado.vue';
import BarraNavegacaoDeslogado from './BarraNavegacaoDeslogado.vue';

import { mapGetters } from 'vuex'

export default {
    components: {
        BarraNavegacaoLogado,
        BarraNavegacaoDeslogado
    },
    computed: {
        ...mapGetters(['usuarioLogado'])
    }
}
</script>

<style>
    .navbar {
        background: #27ae60;
    }
    .navbar-bytebank a {
        color: #fff;
    }
    .navbar-bytebank a:hover {
        color: #000;
    }
</style>
