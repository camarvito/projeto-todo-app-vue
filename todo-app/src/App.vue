<template>
  <div id="app">
      <span>Tarefas</span>
      <ProgressBar />
      <AddTask />
      <TaskGrid :tasks="tasks" />
  </div>
</template>

<script>
import ProgressBar from './components/ProgressBar'
import AddTask from './components/AddTask'
import TaskGrid from './components/TaskGrid'
import Task from './components/Task'

/* A solução que eu vi foi a seguinte, criar uma task grid que tem uma conexão com o data da vue instance e vê os objetos task,
e conforme esse array, renderiza os componentes task, em um v-for. 

Ele estava usando muitos emits de evento, como eu pensei.

- Ele passa o nome no objeto.
- Aparentemente o component task também possui um estado, se a tarefa está ou não feita.

- A progress bar verifica o total de componentes e quantos componentes estão com estado 'realizado' e faz a média com base nisso.
- O addTask emite um evento, passando um objeto do tipo task pra tag pai.

- Passamos como param para a TaskGrid a coleção de objetos task.

--> Programar adicionar objeto no array tasks.
*/

export default {
  name: 'app',
  data() {
    return {
      tasks: []
    }
  },
  methods: {},
  components: { ProgressBar, AddTask, Task, TaskGrid }
}
</script>

<style lang="scss">
#app {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  font-family: 'Lato', sans-serif;
  font-weight: 300;
  font-size: 4rem;
  background: linear-gradient(to right, #536976, #292E49);
  color: #FFF;
  
  height: 100vh;
}

</style>
