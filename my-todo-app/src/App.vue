<template>
  <div class="container">
    <h1>To Do App con Vue.Js</h1>

    <!-- componente: aggiunta dei task -->
    <AddTask @add-task="addTask"/>
    
    <!-- componente: lista dei task -->
    <TaskList 
      :tasks="tasks"
      @remove-task="removeTask"
      />

  </div>  
</template>

<script>
import AddTask from './components/AddTask.vue'
import TaskList from './components/TaskList.vue'

export default {
  components: { AddTask, TaskList },
  data() {
    return {
      // variabili
      tasks : []
    }
  },
  methods: {
    // metodi/funzioni
    addTask(task){
      console.log(task);
      this.tasks.push({ text: task });
      console.log(this.tasks);
    },
    removeTask(index){
      this.tasks.splice(index, 1);
    }
  }

}
</script>


<style scoped>
</style>
