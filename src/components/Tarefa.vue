import Cronometro from './Cronometro.vue';

<template>
  <BoxComponent>
    <div class="columns">
      <div class="column is-7">
        {{tarefa.descricao || 'Tarefa sem descrição'}}
      </div>
      <div class="column">
        <Cronometro :tempoEmSegundos="tarefa.duracaoEmSegundos" />
      </div>
    </div>
  </BoxComponent>
</template>

<script lang="ts">
import { defineComponent, PropType } from "vue";
import Cronometro from "./Cronometro.vue";
import ITarefa from "../interfaces/ITafera";
import BoxComponent from "./Box.vue";
export default defineComponent({
  name: "TarefaComponent",
  components: {
    Cronometro,
    BoxComponent
  },
  props: {
    tarefa: {
      type: Object as PropType <ITarefa>,
      required: true,
    }
  },
});
</script>

