<template>
  <div class="container">
    <h1>To Do App con Vue.Js</h1>

    <!-- componente: aggiunta dei task -->
    <AddTask @add-task="addTask"/>
    
    <!-- componente: lista dei task -->
    <TaskList 
      :tasks="tasks"
      @edit-task="openEditModal"
      @remove-task="removeTask"
    />

    <!-- componente: modale 
        
      TODO: 
        - salvataggio del testo modificato in modale
        - chiusura modale con o senza testo modificato
      -->
    <EditModal
      v-if="selectedTask"
      :task="selectedTask.text"
      @save="saveEdit"
      @close="selectedTask = null"
    />

  </div>  
</template>

<script>
import AddTask from './components/AddTask.vue'
import TaskList from './components/TaskList.vue'
import EditModal from './components/EditModal.vue'

export default {
  components: { AddTask, TaskList, EditModal },
  data() {
    return {
      // variabili
      tasks : JSON.parse(localStorage.getItem('tasks')) || [],
      selectedTask : null
    }
  },
  methods: {
    // metodi/funzioni
    addTask(task){
      this.tasks.push({ text: task });
      this.saveTasks()
    },
    removeTask(index){
      this.tasks.splice(index, 1);
      this.saveTasks()
    },
    openEditModal(task, index){
      // valorizzare il selectedTask
      console.log(task);
      console.log(index);
      console.log(this.selectedTask);
      this.selectedTask = { ...task, index }
    },
    saveEdit(newText){
      this.tasks[this.selectedTask.index] = newText;
      this.selectedTask = null;
    },
    saveTasks(){
      localStorage.setItem('tasks', JSON.stringify(this.tasks))
    }

  }

}
</script>


<style scoped>
</style>
