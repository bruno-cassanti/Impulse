<template>
    <MyUseBox>
        <div class="box has-text-weight-bold">
            <div class="columns">
                <div class="column is-7">
                {{ task.interfaceDescription || 'Tarefa Sem Descrição' }}
                </div>
                <div class="column">
                <MyStopwatch :timeInSeconds="task.durationInSeconds"/>
                </div>
            </div>
        </div>
    </MyUseBox>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import MyStopwatch from './MyStopwatch.vue';
import ITask from '../interface/ITask';
import MyUseBox from './MyUseBox.vue';

export default defineComponent ({
    name: 'MyTask',
    components: {
    MyStopwatch,
    MyUseBox,
},
    props: {
        task: {
            type: Object as PropType<ITask>,
            required: true
        }
    }
})
</script>

<style scoped>
.box {
    background: #F2F3D9;
}
</style>
