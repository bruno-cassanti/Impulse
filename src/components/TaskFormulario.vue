<template>
  <div class="box formulario">
    <div class="columns">
      <div
        class="column is-8"
        role="form"
        aria-label="Formulário para criação de uma nova tarefa"
      >
        <input
          type="text"
          class="input"
          placeholder="Qual tarefa você deseja iniciar?"
          v-model="taskDescription"
        />
      </div>
      <div class="column">
        <MyTimer @finishedTimer="fineshedTask"/>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import MyTimer from './MyTimer.vue';

export default defineComponent({
  name: 'TaskFormulario',
  emits: ['whenSavingTask'],
  components: {
    MyTimer
  },
  data() {
    return {
      taskDescription: ''
    }
  },
  methods: {
    fineshedTask (elapsedTimeNumber: number) : void {
      this.$emit('whenSavingTask', {
        durationInSeconds: elapsedTimeNumber,
        taskDescription: this.taskDescription
      })
      this.taskDescription = ''
    }
  }
});
</script>

<style>
/* Seus estilos aqui */
</style>
