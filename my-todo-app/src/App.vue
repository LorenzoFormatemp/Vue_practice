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
      tasks : [],
      selectedTask : null
    }
  },
  methods: {
    // metodi/funzioni

    /* 2- gestire la modifica
    */
    addTask(task){
      this.tasks.push({ text: task });
    },
    removeTask(index){
      this.tasks.splice(index, 1);
    },
    openEditModal(task, index){
      // valorizzare il selectedTask
      this.selectedTask = { ...task, index }
    },
    saveEdit(newText){
      console.log(newText);
      console.log(this.tasks[this.selectedTask.index]);

      this.tasks[this.selectedTask.index] = newText;
      this.selectedTask = null;
    }

  }

}
</script>


<style scoped>
</style>
