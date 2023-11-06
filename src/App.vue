<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BarraLateral />
    </div>
    <div class="column is-three-quarter">
      <TaskFormulario @whenSavingTask="saveTask"/>
      <div class="list">
        <MyTask v-for="(index, task) in taskList" :key="index" :task="task"/>
        <MyUseBox v-if="emptyList">
        Você não está muito produtivo hoje :(
        </MyUseBox>
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from './components/BarraLateral.vue';
import TaskFormulario from './components/TaskFormulario.vue';
import MyTask from './components/MyTask.vue';
import ITask from './interface/ITask'
import MyUseBox from './components/MyUseBox.vue';


export default defineComponent({
  name: 'App',
  components: {
    BarraLateral,
    TaskFormulario,
    MyTask,
    MyUseBox
},
  data () {
    return {
      taskList: [] as ITask[]
    }
  },
  computed: {
    empemptyList () : boolean {
      return this.taskList.length === 0
    }
  },
  methods: {
    saveTask ( task: ITask ) {
      this.taskList.push(task)
    },
    
  }
});
</script>

<style>
  .list {
    padding: 1.25rem;
  }
</style>
