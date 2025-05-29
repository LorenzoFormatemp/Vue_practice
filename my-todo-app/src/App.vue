<template>
  <div class="container">
    <h1>To Do App con Vue.Js</h1>

    <!-- componente: aggiunta dei task -->
    <AddTask @add-task="addTask"/>
    
    <!-- componente: lista dei task -->

  </div>  
</template>

<script>
import AddTask from './components/AddTask.vue'

export default {
  components: { AddTask },
  data() {
    return {
      // variabili
      tasks : []
    }
  },
  methods: {
    // metodi/funzioni
    addTask(task){      
      this.tasks.push(task);
    }
  }

}
</script>


<style scoped>
</style>
